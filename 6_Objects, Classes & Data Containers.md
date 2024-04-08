# How to write clean Class

1. You typically should prefer many small classes over a few large classes or Classes should have a Single-Responsibility Principle (SRP) (e.g A Product class is responsible for change the product name)
2. Use at least a couple of the available properties (Medium Cohesion)
3. Follow the Law Demeter (e.g `this.customer.lastPurchase.date` change to `this.customer.getLastPurchaseDate()`)
4. Classes should follow SOLID rule
   - **Single-Responsibility Principle**, class only work related with that name (e.g A User class has login, signup and assgnRole)
   - **Open-Closed Principle**, class should be open for extension but closed for modification. We can use Polymorphism
   - **Liskov Substitution Principle**, object should be replaceable with instances of their subsclasses without altering the behavior, We can use Inheritance
   - **Interface Segregation Principle**, many client-specific interface are better than one general purpose interface

# What the difference between Object and Data Container

1. Object
   - Private internals/properties, public API (methods)
   - Contain your business logic(in OOP)
   - Abstractions ever concreations
2. Data Container/Data Structure
   - Public internals/properties, (almost) no API (methods)
   - Store and transport data
   - Concretions only

# What is a Polymorphism

Polymorphism literally means "many forms" and in computer science, specifically object-oriented programming, it refers to the ability of objects to respond differently to the same message. Or it is like classification (e.g. Animal has Cat and Dog)

## Example Polymorphism

```Typescript
type Purchase = any;

let Logistics: any;

interface Delivery {
    deliverProduct();
    trackProduct();
}

class DeliveryImplementation {
  protected purchase: Purchase;

  constructor(purchase: Purchase) {
    this.purchase = purchase;
  }
}

class ExpressDelivery extends DeliveryImplementation implements Delivery {
    deliverProduct() {
        Logistics.issueExpressDelivery(this.purchase.product)
    }

    trackProduct() {
        Logistics.trackExpressDelivery(this.purchase.product);
    }
}

class InsuredDelivery extends DeliveryImplementation implements Delivery {
    deliverProduct() {
        Logistics.issueInsuredDelivery(this.purchase.product);
    }

    trackProduct() {
        Logistics.trackInsuredDelivery(this.purchase.product);
    }
}

class StandardDelivery extends DeliveryImplementation implements Delivery {
    deliverProduct() {
        Logistics.issueStandardDelivery(this.purchase.product);
    }

    trackProduct() {
        Logistics.trackStandardDelivery(this.purchase.product);
    }
}

function createDlivery(purchase) {
    if(purchase.deliveryType === 'express') {
        delivery = new ExpressDelivery(purchase)
    } else if(purchase.deliveryType === 'insured') {
        delivery = new InsuredDelivery(purchase)
    } else {
        delivery = new StandardDelivery(purchase)
    }

    return delivery

}
    let delivery: Delivery = createDelivery({});

    delivery.deliverProduct();

```
