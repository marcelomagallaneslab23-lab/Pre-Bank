# Pre-Banco

**Objetivo**

Simular una entidad bancaria donde los usarios puedan:

1. Depositar fondos
2. Retirar fondos
3. Consltar su saldo
4. El administrador pueda ver el total de fondos del sistema

**Estructura del Contrato**
Control de acceso
1. Solo el **admin** puede ver el balance total del contrato
2. Los usaurios solo pueden retirar su propio saldo.

**Manipulacion de Ether**
1. depositar() es payable y actualizar el saldo del usuario
2. retirar(uint256 monto) tranfiere Ether al usuario si tiene saldo suficiente
   
**Mappings**
1. Se utiliza un mapping(address => uint256) para almacenar el saldo de cada usuario.

**Variables de tipo address**
1. Se usa msg.sender para identificar al usuario que interactúa con el contrato.
2. El admin es una variable immutable.

**Manejo de errores**
1. Se implementan errores personalizados como SaldoInsuficiente y AccesoDenegado.

**Modificadores**
1. Se usa modifier soloAdmin para restringir funciones al administrador.
2. Se puede usar modifier tieneSaldo(uint256 monto) para validar retiros.

**Constructor**
1. Define el admin al momento de desplegar el contrato.

**Variables immutable y constant**
1. admin es immutable.
2. Se puede definir una comisión fija como constant.

**Buenas prácticas**
1. Uso de eventos para registrar depósitos y retiros.
2. Validación de errores antes de transferencias.
3. Separación de lógica en funciones privadas.

**Implementación**
1. El contrato fue desplegado en la red de prueba Sepolia usando Remix.
2. Se puede interactuar con el contrato usando MetaMask y Remix IDE.

**Repositorio**
Cómo clonar y ejecutar: https://github.com/marcelomagallaneslab23-lab/Pre-Bank.git
1. Abre el archivo .sol en Remix IDE.
2. Selecciona la red de prueba (Sepolia).
3. Conecta MetaMask.
4. Despliega el contrato y prueba las funciones.

