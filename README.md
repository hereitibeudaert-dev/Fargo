import requests
import os

def download_file_sync(url, filename):
    """Скачивает файл синхронно и сохраняет его."""
    print(f"Начинается скачивание: {url}...")
    try:
        # Stream=True позволяет скачивать файл кусками, а не загружать весь в память
        with requests.get(url, stream=True) as r:
            r.raise_for_status() # Вызывает исключение для плохих ответов (4xx или 5xx)
            
            # Получаем общий размер файла, если доступен
            total_size = int(r.headers.get('content-length', 0))
            
            # Открываем файл для записи в бинарном режиме
            with open(filename, 'wb') as f:
                downloaded_size = 0
                chunk_size = 8192 # Размер куска (8KB)
                
                for chunk in r.iter_content(chunk_size=chunk_size):
                    # Отфильтровываем пустые куски
                    if chunk:
                        f.write(chunk)
                        downloaded_size += len(chunk)
                        
                        # Отображение прогресса
                        if total_size > 0:
                            percent = (downloaded_size / total_size) * 100
                            # \r возвращает курсор в начало строки для обновления
                            print(f"\rПрогресс: {downloaded_size / (1024*1024):.2f} MB / {total_size / (1024*1024):.2f} MB ({percent:.1f}%)", end='')

        print(f"\n✅ Скачивание завершено. Файл сохранен как: {filename}")
        
    except requests.exceptions.RequestException as e:
        print(f"\n❌ Ошибка скачивания: {e}")

# --- Использование ---
# URL большого файла для примера
FILE_URL = "http://speedtest.tele2.net/100MB.zip" 
OUTPUT_NAME = "100MB_test_file.zip"

if __name__ == "__main__":
    download_file_sync(FILE_URL, OUTPUT_NAME)
