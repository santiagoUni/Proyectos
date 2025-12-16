# INSTALACIÓN EN VISUAL STUDIO CODE

## 1. REQUISITOS
- Node.js 18+ (descargar de https://nodejs.org/)
- npm (viene con Node.js)
- Visual Studio Code (https://code.visualstudio.com/)

## 2. PASOS DE INSTALACIÓN

### Opción A: Desde carpeta descargada
```bash
# 1. Extraer el archivo ZIP descargado
# 2. Abrir Visual Studio Code
# 3. File → Open Folder → Seleccionar la carpeta del proyecto
# 4. Abrir terminal en VS Code (Terminal → New Terminal)
# 5. Ejecutar:

npm install
npm run dev:client
```

### Opción B: Desde GitHub
```bash
git clone https://github.com/usuario/proyecto-santiago-ocampo.git
cd proyecto-santiago-ocampo
npm install
npm run dev:client
```

## 3. ACCEDER A LA APLICACIÓN
- Abrir navegador: http://localhost:5000
- La aplicación se recargará automáticamente al hacer cambios

## 4. COMANDOS DISPONIBLES
```bash
npm run dev:client      # Ejecutar en desarrollo (http://localhost:5000)
npm run check           # Verificar tipos TypeScript
npm run build           # Compilar para producción
npm run dev:client -- --port 3000  # Cambiar puerto si 5000 está ocupado
```

## 5. ESTRUCTURA DEL PROYECTO
```
proyecto-santiago-ocampo/
├── client/
│   ├── src/
│   │   ├── components/      # Componentes React
│   │   ├── lib/             # Lógica MLP, algoritmos
│   │   ├── pages/           # Páginas principales
│   │   └── main.tsx
│   └── index.html
├── package.json             # Dependencias
├── vite.config.ts          # Configuración Vite
├── tsconfig.json           # Configuración TypeScript
└── README.md               # Este archivo
```

## 6. SOLUCIÓN DE PROBLEMAS

### Puerto 5000 ya está en uso
```bash
npm run dev:client -- --port 3000
```

### Node.js no reconocido
- Reiniciar Visual Studio Code después de instalar Node.js

### Errores de módulos
```bash
rm -rf node_modules package-lock.json
npm install
```

## 7. DESARROLLO

### Agregar nuevas dependencias
```bash
npm install nombre-del-paquete
```

### Modificar la red neuronal
- Editar: `client/src/lib/mlp.ts`
- Cambiar: hidden_nodes, learning_rate, función de activación

### Crear nuevas páginas
1. Crear archivo en `client/src/pages/nueva-pagina.tsx`
2. Registrar en `client/src/App.tsx`

## 8. COMPILAR PARA PRODUCCIÓN
```bash
npm run build
```
Los archivos compilados estarán en `dist/`
