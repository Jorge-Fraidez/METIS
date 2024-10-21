# METIS

Este es el proyecto **METIS**, desarrollado por [Jorge Fraidez](https://github.com/Jorge-Fraidez), [Maricruz Torres](https://github.com/Maricruz1900) y [Fernanda Rodríguez](https://github.com/Mafer-Rodriguez) para la Hackathon virtual. Este repositorio contiene el código fuente de las aplicaciones desarrolladas en **React**, así
como de los canister de **Rust**.

## Requisitos

Antes de comenzar, asegúrate de tener instaladas las siguientes herramientas:

- [Node.js](https://nodejs.org/) (versión 14 o superior)
- [Git](https://git-scm.com/)
- [DFX](https://internetcomputer.org/docs/current/developer-docs/getting-started/install/) (version 24)
- [Cargo](https://doc.rust-lang.org/cargo/)

## Clonar el Repositorio

Para clonar este repositorio, sigue estos pasos:

1. Abre tu terminal o línea de comandos.
2. Ejecuta el siguiente comando:

   ```bash
   git clone https://github.com/Jorge-Fraidez/METIS.git

3. Navega a la carpeta generada

   ```bash
   cd METIS

3. Instala las dependencias globales

   ```bash
   npm install

4. Navega a la carpeta react-dashboard e instala las dependencias y declaraciones locales

   ```bash
   cd react-dashboard
   npm install
   dfx generate network nlp vectordb

5. Navega a la raíz del proyecto e inicia la réplica de dfx

    ```bash
    cd ../../
    dfx start --background --clean

6. Obten el id del canister internet_identity, vectordb, newtwork y nlp

    ```bash
    dfx canister id internet_identity
    dfx canister id qrcode
    dfx canister id newtwork
    dfx canister id nlp
    dfx canister id vectordb

   Los IDs serán mostrados en el orden de ejecución

7. Navega a react-dashboard y crea un archivo .env

   ```bash
   cd ../react-dashboard
   touch .env
   ```
   Añade lo siguiente
  ```bash
   VITE_CANISTER_ID_NETWORK='NETWORK_CANISTER_ID'
   VITE_CANISTER_ID_NLP='NLP_CANISTER_ID'
   VITE_CANISTER_ID_VECTORDB='VECTORDB_CANISTER_ID'
   VITE_REACT_APP_INTERNET_COMPUTER_PROVIDER='INTERNET_IDENTITY_CANISTER_ID.localhost:4943/'
  ```

8. Vuelve a la raíz del proyecto y despliega el proyecto

    ```bash
    cd ../..
    dfx deploy