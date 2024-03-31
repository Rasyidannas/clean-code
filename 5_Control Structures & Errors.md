# Control Structures & Errors

## How to Keep Your Control Structure Clean?

1. Avoid Deep Nesting
   - Using Factory Functions and Polymorphism
   - Utilize Error
2. Prefer Positive Checks (if isEmpty vs isNotEmpty)
3. Use Guards & Fail Fast
   - Example:
     - `if(!email.includes(@))`
     - `if(!user.active)`
     - `if(!user.hasPurchases())`

## Example of Control Structures & Error

1. Control Structures

```Javascript
main();

function main() {
  const transactions = [
    {
      id: 't1',
      type: 'PAYMENT',
      status: 'OPEN',
      method: 'CREDIT_CARD',
      amount: '23.99',
    },
    {
      id: 't2',
      type: 'PAYMENT',
      status: 'OPEN',
      method: 'PAYPAL',
      amount: '100.43',
    },
    {
      id: 't3',
      type: 'REFUND',
      status: 'OPEN',
      method: 'CREDIT_CARD',
      amount: '10.99',
    },
    {
      id: 't4',
      type: 'PAYMENT',
      status: 'CLOSED',
      method: 'PLAN',
      amount: '15.99',
    },
  ];

  try {
    processTransactions(transactions);
  } catch(error) {
    showErrorMessage(error.message)
  }
}

function processTransactions(transactions) {
  validateTransaction(transactions);

  for (const transaction of transactions) {
    processTransaction(transaction);
  }
}

function validateTransaction(transaction) {
  if (isEmpty(transaction)) {
    const error = new Error('No transactions provided!')
    error.code = 1
    throw error
  }
}

function isEmpty(transactions) {
  return !transactions || transactions.length === 0;
}

function showErrorMessage(message, item) {
  console.log(message);
  if (item) {
    console.log(item);
  }
}

function processTransaction(transaction) {
  try {
    validateTransaction(transaction);

    processWithProcessor(transaction);
  } catch(error) {
    showErrorMessage(error.message, error.item)
  }
}

//this is a function polymorphism
function processWithProcessor(transaction) {
  const processors = getTransactionProcessors(transaction);

  if(isPayment(transaction)) {
    processors.processPayment(transaction);
  } else {
    processors.processRefund(transaction);
  }
}

function getTransactionProcessors(transaction) {
  let processors = {
    processPayment: null,
    processRefund: null
  }

  if (usesTransactionMethod(transaction, 'CREDIT_CARD')) {
    processors.processPayment = processCreditCardPayment;
    processors.processRefund = processCreditCardRefund;
  } else if (usesTransactionMethod(transaction, 'PAYPAL')) {
    processors.processPayment = processPaypalPayment;
    processors.processRefund = processPaypalRefund;
  } else if (usesTransactionMethod(transaction, 'PLAN')) {
    processors.processPayment = processPlanPayment;
    processors.processRefund = processPlanRefund;
  }

  return processors;
}

function isOpen(transaction) {
  return transaction.status === 'OPEN';
}

function validateTransaction(transaction) {
  if (!isOpen(transaction)) {
    const error = new Error('Invalid transaction type.');
    throw error
    return;
  }

  if (!isPayment(transaction) && !isRefund(transaction)) {
    const error = new Error('Invalid transaction type!');
    error.item = transaction;
    throw error;
  }
}

function usesTransactionMethod(transaction, method) {
  return transaction.method === method;
}

function isPayment(transaction) {
  return transaction.type === 'PAYMENT';
}

function isRefund(transaction) {
  return transaction.type === 'REFUND';
}

function processCreditCardPayment(transaction) {
  console.log(
    'Processing credit card payment for amount: ' + transaction.amount
  );
}

function processCreditCardRefund(transaction) {
  console.log(
    'Processing credit card refund for amount: ' + transaction.amount
  );
}

function processPayPalPayment(transaction) {
  console.log('Processing PayPal payment for amount: ' + transaction.amount);
}

function processPayPalRefund(transaction) {
  console.log('Processing PayPal refund for amount: ' + transaction.amount);
}

function processPlanPayment(transaction) {
  console.log('Processing plan payment for amount: ' + transaction.amount);
}

function processPlanRefund(transaction) {
  console.log('Processing plan refund for amount: ' + transaction.amount);
}
```
