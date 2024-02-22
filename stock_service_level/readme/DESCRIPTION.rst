Base module to manage route / reservation rules per service level.

This module enhances Odoo with service level capabilities for stock moves.
It enables differentiation of service offerings for the same physical product.

A service level refers to a distinct type of service provision associated
with a product. It allows for selling a product with various service
offerings or levels, facilitating customized customer experiences.

Features:

- Enables selling/requesting the same physical product with different service levels.
- Avoids splitting products into separate procurement groups, preserving
  flexibility in logistics chain operations.
- Allows definition of different routes for products based on service level.
- Supports application of distinct reservation rules depending on service
  level.


The module integrates seamlessly with Odoo's stock management system.
Users can configure service levels and associated rules through the
interface, enabling efficient management of product variants and service
offerings within the logistics framework.


Implementation roadmap in different modules:

Module `stock_service_level` in oca/wms:

* [x] Creating `stock.service.level` model
* [x] link `stock.move` to service level model
* [x] propagated service level information over procurement mechanisms

Module `stock_service_level_route` in oca/wms:

* [x] allow to select proper stock rule/route based on service level
* [ ] to split in a dedicated PR

Module `sale_stock_service_level` in oca/sale-workfow:

* [ ] allow to select the level of service on sale order / sale order line
      and propagate the information while generating the procurement


Module `stock_request_service_level` in oca/sale-logistics-warehouse:

* [ ] allow to select the level of service on stock request order / stock
      request order line and propagate the information while generating
      the procurement

Not sure if this will be part of the same module (maybe there is nothing to do?):

* [ ] make sure we can easily hook the reservation system to change rules
      according the level of service for a specific product 
