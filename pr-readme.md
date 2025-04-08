# 🧪 Flujo de Trabajo con Git y Pull Requests

Este proyecto utiliza un flujo de trabajo basado en ramas para mantener el código limpio, organizado y listo para producción.



## 🌳 Estructura de Ramas

| Rama        | Propósito                                                                |
|-------------|--------------------------------------------------------------------------|
| `main`      | Código listo para producción; representa la versión estable y final.     |
| `dev`       | Desarrollo; se integra y prueba nuevas funcionalidades antes de pasarlas a producción. |
| `feature/*` | Ramas para nuevas funcionalidades; se crean desde `dev`.                 |
| `bugfix/*`  | Ramas para corregir errores detectados en la etapa de desarrollo (`dev`).  |
| `hotfix/*`  | Ramas para correcciones urgentes en producción; se crean desde `main` y se fusionan en `dev` posteriormente. |


## 🏷️ Convenciones para nombrar Commits

Se utiliza el formato `<tipo>: <descripción breve>`:



### ✨ Nuevas Funcionalidades (`feat:`)
- `feat:add-cart`
- `feat:add-product-endpoint`
- `feat:create-auth-module`


### 🐛 Corrección de Errores (`fix:`)
- `fix:fix-login`
- `fix:fix-product-dto`
- `fix:fix-validation-error`


### ⚡ Mejoras de Rendimiento (`perf:`)
- `perf:optimize-image-loading`
- `perf:optimize-db-queries`
- `perf:reduce-bundle-size`


### 🛠️ Cambios en Build o Deploy (`build:`)
- `build:add-dockerfile`
- `build:configure-build-system`
- `build:setup-deploy-scripts`


### 🤖 Integración Continua (`ci:`)
- `ci:setup-github-actions`
- `ci:fix-ci-build`
- `ci:update-pipeline`


### 📝 Documentación (`docs:`)
- `docs:update-readme`
- `docs:add-api-docs`
- `docs:update-changelog`


### ♻️ Refactorización `(refactor:`)
- `refactor:rename-variable`
- `refactor:reorganize-services`
- `refactor:simplify-function`


### 🎨 Estilos y Formato (`style:`)
- `style:apply-prettier`
- `style:fix-indentation`
- `style:update-code-formatting`

### ✅ Pruebas (`test:`)
- `test:add-new-tests`
- `test:fix-failing-tests`
- `test:update-test-cases`




## 🧷 Convenciones para nombrar Ramas

Se utiliza el formato `<tipo>/<descripción>`:

### ✨ Funcionalidades Nuevas (`feature/`)

- `feature/add-cart`  
- `feature/add-product-endpoint`  
- `feature/create-auth-module`

### 🐛 Corrección de Errores en Desarrollo (`bugfix/`)

- `bugfix/fix-login`  
- `bugfix/fix-product-dto`  
- `bugfix/fix-validation-error`

### 🚨 Parche Urgente en Producción (`hotfix/`)

- `hotfix/fix-env-vars`  
- `hotfix/fix-payment-gateway`


## 🔁 Flujo de Trabajo

### 1. Crear una Nueva Rama para la Funcionalidad o Corrección

1. Desde la rama `dev`, actualiza y crea la nueva rama:

   ```bash
   git checkout dev
   git pull origin dev
   git checkout -b feature/nueva-funcionalidad
    ```
2. Realiza tus cambios, commits y sube la rama:

    ```bash 
    git push -u origin feature/nueva-funcionalidad
    ```

## 2. Crear el Pull Request (PR)
- Para funcionalidades y correcciones:
Se crea un PR desde la rama feature/* o bugfix/* hacia la rama dev.

- Validaciones del PR:
    - Código limpio y sin comentarios innecesarios

    - Ausencia de archivos sensibles (por ejemplo, .env)

    - PR con nombre y descripción claros

    - Pruebas locales o con tests automatizados

## 3. Integrar Cambios en Producción
- Cuando la rama dev esté aprobada y probada, se crea un PR de dev hacia main para desplegar la versión estable en producción.

## 4. Manejo de Hotfixes en Producción
1. Para corregir un error urgente en producción:

```bash
git checkout main
git pull origin main
git checkout -b hotfix/nombre-del-hotfix
```
2. Realiza los cambios, commits y sube la rama:
```bash
git push -u origin hotfix/nombre-del-hotfix
```
3. Crea un PR de hotfix/* hacia main.

**Importante**: Una vez fusionado, integra el hotfix también en dev para sincronizar las correcciones.
a





