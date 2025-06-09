🧾 Trabajo Final - Módulo 2
Subasta: Smart Contract
Debes crear un smart contract y desplegarlo desde tu propia dirección.

🎯 Requisitos Generales
- Cada smart contract debe estar:
  - ✅ Publicado en la red Sepolia.
  - ✅ Verificado (con el código fuente accesible).
- La URL del contrato publicado y verificado debe incluirse en esta sección:
  - TRABAJO FINAL MÓDULO 2
- Así mismo una URL del repositorio público en Github.

⚙️ Funcionalidades Requeridas
# contract Auction

- 📦 Constructor
  - Inicializa la subasta con los parámetros necesarios para su funcionamiento.
  ### constructor (uint256 bidTime)
    
- 🏷️ Función para ofertar
  - Permite a los participantes ofertar por el artículo.
  - Una oferta es válida si:
    - Es mayor en al menos 5% que la mayor oferta actual.
    - Se realiza mientras la subasta está activa.
  ### // sendBid: send a new bid for auction
  ### function sendBid() external payable isAuctionActive
      
- 🥇 Mostrar ganador
  - Devuelve el oferente ganador y el valor de la oferta ganadora.
  ### // getWinner: return winner and amount
  ### function getWinner() external view isAuctionFinished returns (address)
    
- 📜 Mostrar ofertas
  - Devuelve la lista de oferentes y sus respectivos montos ofrecidos.
  ### // getBids: return lists of biders and amounts
  ### function getBids() external view returns (address[] memory, uint256[] memory)


- 💸 Devolver depósitos
  - Al finalizar la subasta:
    - Se devuelve el depósito a los oferentes no ganadores.
    - Se descuenta una comisión del 2%.
  ### // returnBids: return bid's amount to biders that do not win
  ### function returnBids() internal isAuctionFinished

💰 Manejo de depósitos
  - Las ofertas deben:
    - Ser depositadas en el contrato.
    - Estar asociadas a las direcciones de los oferentes.

📢 Eventos requeridos
  - Nueva Oferta: Emitido cuando se realiza una nueva oferta.
  - Subasta Finalizada: Emitido cuando finaliza la subasta.
  ### // events
  ### event newBid(address indexed bider, uint256 amount);
  ### event IsAuctionFinished(address indexed bider, uint256 amount);

🚀 Funcionalidades Avanzadas
🔁 Reembolso parcial
Durante la subasta, los participantes pueden retirar el importe por encima de su última oferta válida.

Ejemplo:

Tiempo	Usuario	Oferta
- T0	Usuario 1	1 ETH
- T1	Usuario 2	2 ETH
- T2	Usuario 1	3 ETH
- → Usuario 1 puede pedir el reembolso de la oferta T0 (1 ETH).

### // withdrawDeposit: for a bider, keep the last bid and withdraw the previous amount
### function withdrawDeposit() external isAuctionFinished 

🧠 Consideraciones Adicionales
- Se deben utilizar modificadores cuando sea conveniente.
  ### modifier onlyOwner()
  ### modifier isAuctionActive()
  ### modifier isAuctionFinished()

- Para superar la mejor oferta, la nueva debe ser superior al menos en 5%.
- Si una oferta válida se realiza dentro de los últimos 10 minutos, el plazo de la subasta se extiende 10 minutos más.
- El contrato debe ser seguro y robusto. Manejando adecuadamente los errores y las posibles situaciones excepcionales.
- Se deben utilizar eventos para comunicar los cambios de estado de la subasta a los participantes.
- La documentación del contrato debe ser clara y completa en un archivo README.md en el repositorio en GitHub, explicando:
  - Funciones
  - Variables
  - Eventos

📍 Entrega
- El trabajo debe ser presentado en la sección TRABAJO FINAL MÓDULO 2, incluyendo solo la URL del contrato publicado y verificado.
- También debe enviarse un repositorio público en Github que sirva a manera de documentación, explicando la manera en que está construida la subasta.

🗓️ Fechas importantes para la entrega
- 03.06 → Se informa la consigna del trabajo final.
- 08.06 → 🟢 Soft deadline:
Quienes entreguen entre el 03.06 y el 08.06 a las 23:59 horas inclusive, podrán recibir correcciones, hacer ajustes y volver a entregar una versión mejorada del trabajo.
- 11.06 → 🔴 Hard deadline:
Quienes entreguen entre el 09.06 y el 11.06 a las 23:59 horas inclusive, recibirán corrección únicamente sobre lo entregado, sin posibilidad de hacer cambios posteriores.
- No se aceptarán trabajos prácticos una vez cumplido el hard dealine.
