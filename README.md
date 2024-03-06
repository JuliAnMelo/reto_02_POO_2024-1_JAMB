# reto_02_POO_2024-1_JAMB

# Diagrama de clases UML: Cafetería

Muestra a la Cafetería como concepto, como punto de conexión de las relaciones entre el sitio físico, el personal, el menú, el dueño y los clientes.

```mermaid

classDiagram
    Owner *-- Cafeteria
    Owner : +string name
    Owner : pay_staff()
    Owner : pay_bills()
    Owner : pay_receipts()
    Owner : manage()
    Owner : divulge()

    Cafeteria *-- Menu
    Cafeteria *-- Staff
    Cafeteria *-- Site
    Cafeteria : +string name
    Cafeteria : +int opening_hours
    Cafeteria : +int delivery_schedule
    Cafeteria : +bool open
    Cafeteria :opening_protocol()
    Cafeteria :closing_protocol()


    Menu *-- Drink
    Menu *-- Food
    Menu : +int prize
    Menu : +string size
    Menu : +string description
    Menu : +string recipe
    Menu: +mise_en_place()
    Menu: +preparation()

    Drink <|-- Milkshake
    Drink <|-- Capuccino
    Drink <|-- Frappe
    Drink <|-- Cocoa
    Drink : +bool sugar
    Drink : +to_refill()
    class Milkshake{
      +String Glass
      +int ice_cream1
      +int milk
      +string fruit1
      +to_melt()
    }
    class Capuccino{
      +String Cup
      +int coffee
      +int water
      -to_get_cold()
    }
    class Frappe{
      +String Glass
      +int ice
      +int water
      +string fruit1
      +int chantilly
      +int topping
      +to_melt()
    }
    class Cocoa{
      +String Cup
      +int cocoa
      +int milk
      +int marshmallow
      -to_get_cold()
    }

    Food <|-- Salad
    Food <|-- Ice_Cream_Cup
    Food <|-- Cake
    Food : +string Plate 
    Food : +int topping
    class Salad{
      +string fruit1
      +string fruit2
      +string fruit3
      +string fruit4
      +int cream 
      +to_get_warm()
    }
    class Ice_Cream_Cup{
      +int ice_cream1
      +int ice_cream2
      +int ice_cream3
      +int syrup
      +to_melt()
    }
    class Cake{
      +string fruit1
      +int syrup
      +to_get_stale()
    }


    Staff <|-- Manager
    Staff <|-- Barista
    Staff <|-- Waiter
    Staff <|-- Cashier
    Staff <|-- Dishwasher
    Staff <|-- Baker
    Staff : +string name
    Staff : +int working_hours
    Staff : +bool working
    Staff : +int salary
    Staff : +int shift_schedule
    Staff :get_paid()
    Staff :get_fired()

    class Manager{
        +recommend()
        +admonish()
        +congratulate()
        }
    class Barista{
        +prepare_drink()
        +clean()
        +divulge()
        }
    class Waiter{
        +guide()
        +divulge()
        +serve()
        }
    class Cashier{
        +receive()
        +count()
        +return()
        }
    class Dishwasher{
        +wash_dishes()
        +clean()
        +sanitize()
        }
    class Baker{
        +prepare_food()
        +clean()
        +store_food()
        }

    Site *-- Furniture
    Site *-- Machinery
    Site : +to_clean()
    Site : +to_sanitize()

    Furniture <|-- Chairs
    Furniture <|-- Tables
    Furniture <|-- Sofas
    Furniture : +int color
    Furniture : +string size
    Furniture : +int amount
    Furniture : +int number
    Furniture : +to_be_used()

    Machinery <|-- Expresso_Machine
    Machinery <|-- Oven
    Machinery <|-- Freezer
    Machinery <|-- Cash_Register
    Machinery : +string characteristics
    Machinery : +string instructions
    Machinery : +to_operate()

    Costumer <|--|> Barista
    Costumer <|--|> Waiter
    Costumer <|--|> Menu
    Costumer <|--|> Furniture
    Costumer : +string favorite_food/Drink
    Costumer : + drink()
    Costumer : + eat()
    Costumer : + pay()
    Costumer : + enter()
    Costumer : + sit()
    Costumer : + leave()

```
