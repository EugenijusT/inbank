// app-injected-script.js

(function() {
  // Get product price from Shopify liquid variable
  var productPrice = meta.product.variants[0].price; // in cents

  // Show calculator if price >= 50 euros (5000 cents)
  if (productPrice >= 5000) {
    var ibCalculatorDiv = document.createElement('div');
    ibCalculatorDiv.id = 'ib_calculator';
    var addToCartBtn = document.querySelector('form[action*="/cart/add"]');
    addToCartBtn.parentNode.insertBefore(ibCalculatorDiv, addToCartBtn);

    var script = document.createElement('script');
    script.async = true;
    script.src = 'https://skaiciuokles.inbank.lt/js/calculator';
    document.body.appendChild(script);

    script.onload = function() {
      _ibCalculator('init', {
        calcKey: '3bbfcab4bec33aefc06cd104fe0cf20c',
        layout: 'ib-003',
        colorScheme: 4,
        element: 'ib_calculator',
        amountTotal: productPrice,
        amountAdvance: 0,
        term: 18,
        selectPrice: false,
      });
    };
  }
})();
