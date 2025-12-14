{
  "name": "mobile-banking-app",
  "version": "1.0.0",
  "description": "Мобильное приложение для безопасного и удобного банкинга на React Native.",
  "main": "index.js",
  "scripts": {
    "start": "expo start",
    "android": "expo run:android",
    "ios": "expo run:ios",
    "web": "expo start --web",
    "test": "jest",
    "lint": "eslint . --ext .js,.jsx,.ts,.tsx",
    "prettier": "prettier --write 'src/**/*.{js,jsx,ts,tsx,json,css,scss,md}'"
  },
  "dependencies": {
    "react": "18.2.0",
    "react-native": "0.74.0",
    "expo": "~51.0.0",
    "expo-status-bar": "~1.12.1",
    "expo-secure-store": "~13.0.1",      // Безопасное хранение токенов (аналог FlutterSecureStorage)
    
    // 🗺️ Навигация
    "@react-navigation/native": "^6.1.17",
    "@react-navigation/native-stack": "^6.9.26",
    
    // 🔄 Управление состоянием (пример использования Redux Toolkit)
    "@reduxjs/toolkit": "^2.2.5",
    "react-redux": "^9.1.2",
    
    // 🌐 HTTP-клиент
    "axios": "^1.6.8",                   // Популярный клиент для API
    
    // 🎨 UI и стилизация
    "react-native-safe-area-context": "4.10.1",
    "react-native-screens": "3.31.1",
    "react-native-vector-icons": "^10.0.3", // Иконки
    
    // 🗓️ Форматирование (для валют, дат)
    "moment": "^2.30.1"
  },
  "devDependencies": {
    "@babel/core": "^7.20.0",
    
    // 🧪 Тестирование
    "jest": "^29.2.1",
    "jest-expo": "~51.0.1",
    
    // 🧹 Линтинг и форматирование
    "@types/react": "~18.2.45",
    "@types/react-native": "~0.73.0",
    "typescript": "5.3.3",
    "@typescript-eslint/eslint-plugin": "^7.8.0",
    "@typescript-eslint/parser": "^7.8.0",
    "eslint": "^8.57.0",
    "eslint-plugin-react":
