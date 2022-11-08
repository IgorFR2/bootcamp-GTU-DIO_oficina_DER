# bootcamp-GTU-DIO_oficina_DER
Bootcamp exercise to create an auto workshop entity-relationship diagram.

# Entities
* client - Customer
  * client_id (int) - Customer id.
  * nome (text) -Customer name.
  * telefone (varchar(14)) - Customer phone number (Brazilian pattern Without special chars: (+55)(99) 9 9999-9999).
  * email (text) - Customer email.
* endereco - Address
  * pais (varchar(2)) - BR, CA, NZ, DE, JP, CH, IS, US, IL, etc.
  * estado (varchar(50)) - State.
  * cidade (varchar(50)) - City.
  * logradouro (varchar(50)) - Street, road, boulevard or similar's name.
  * numero (varchar(10)) - Building/Apt number (ex: 123, 134 apt. 505, 123-B-505)
  * complemento (varchar(50)) - House, loft, mansion, igloo, etc.
* veiculo - Car registry
  * veiculo_id (int) - Car's id (generated).
  * placa (varchar(7)) - Car's plate (Mercosul patter).
  * modelo (text) - Car's model.
  * ano (smallint) - Car's year fabrication.
  * cor (varchar(30)) - Car's color.
* ordem_servico - Service order
  * ordem_servico_id (int) - Order id. One or more services compond an order.
  * cliente_id (int) - Client id.
  * data_emissao (timestamptz) - Registry date.
  * status_id (int) - Order status id.
  * data_conclusao (date) - Date when all services were completed.
  * veiculo_id (int) - Car id.
* mecanico - Employee
  * mecanico_id (int) - Employee id. He'll evaluate and make the service.
  * nome (text) - Employee name.
  * endereco_id (int) - Employee address.
  * especialidade (text) - Employee speciality.
* equipe - Team
  * mecanico_id (int) - Employees designated for an order.
  * ordem_servico_id (int) - Service order id.
* servico - Services avaliable
  * servico_id (int) - Service id.
  * valor (int) - Service's cost.
  * estimativa_dias (int) - Estimated time (in days) for the service.
* servico_contratado
  * ordem_servico_id (int) - Order id.
  * servico_id (int) - Service id.
  * valor (int) - Total service value (service and used components).
  * status_id (int) - Service status id.
* peca - Components avaliable 
  * peca_id (int) - Component id.
  * valor (int) - Price.
  * estoque (int) - Number of components avaliable.
* peca_servico
  * ordem_servico_id (int) - Order id.
  * servico_id (int) - Service id.
  * peca_id (int) - Used component id.
  * quantidade (int) - Quantity of used components.
* status - List of possible statuses for servicse and orders.
  * status_id (int) - Status id.
  * status (text) - Satatus description.
