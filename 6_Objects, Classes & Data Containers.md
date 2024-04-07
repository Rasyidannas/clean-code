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

Polymorphism literally means "many forms" and in computer science, specifically object-oriented programming, it refers to the ability of objects to respond differently to the same message. Or it is like classification (Animal has Cat and Dog)

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
