# Cypress-Monkey
Version Modificada de Cypress-Monkey para correr sobre Ghost.

## Requesitos para ejecutar:
1. Tener instalado Ghost y haber creado una cuenta Ghost.
2. Node 18 o mayor

## Como ejecutar
1. Correr Ghost de manera local, e inicar sesion.
2. Corra el comando:
   ```
   npm install
   ```
4. Dirigirse a los archivos monkey-config.json y smart-monkey-config.json en la raiz del proyecto y modificar el script:
   ```
   "baseUrl":"http://localhost:2368/ghost/#",
   ```
5. Modificar tambien los archivos monkey.js y smart-monkey.js en la ruta 
   ```
   Cypress-Monkey > cypress > integration > monkey
   ```
   ```
   const url = Cypress.config('baseUrl') || "http://localhost:2368/ghost/#",
   ```
 6. En la misma ruta para los mismo archivos (monkey.js y smart-monkey.js) dirigirse hasta el método describe y actualizar el siguiente script:
     ```
     cy.get('form').within(() => {
                cy.get('#identification').type('my-user-ghost')
                cy.get('#password').type('my-pass-ghost')
                cy.get('#ember5').click()
     })
     ```
 7. para correr monkeys aplique el siguiente comando en la terminal.
    ```
    npm run monkey
    ```
 8. para correr smart-monkeys aplique el siguiente comando en la terminal.
    ```
    npm run smart-monkey
    ```
Con estos pasos serán más que suficientes para que puedan correr las pruebas y ver en vivo las pruebas.
