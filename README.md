# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```
|-- src/
    |-- apis/               # Dùng để khởi tạo các api function
    |-- assets/             # Chứa các file tài nguyên (images, fonts, icons, etc.)
    |-- components/         # Chứa các components
    |-- constants/          # Chứa các file constant
    |-- types/              # Dùng để chứa các file định nghĩa type
    |-- hooks/              # Chứa hook custom
    |-- layouts/            # Chứa các layout component
    |-- pages/              # Chứa các trang của dự án
    |-- lib/                # Chứa các file config của thư viện bên ngoài
    |-- providers/          # Chứa các providers (theme, store, etc.)
    |-- schemas/            # Chứa các schemas validate ( zod, yup, ...)
    |-- stores/             # Quản lý state (Redux, MobX, etc.)
    |-- styles/             # Quản lý các css global hoặc thư viện scss
    |-- utils/              # Chứa các hàm dùng chung của dự án
    |-- App.tsx             # Định nghĩa root file
    |-- routes.tsx          # Định nghĩa router
