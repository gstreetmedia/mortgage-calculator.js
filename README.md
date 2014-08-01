Mortgage Calculator
=================================
This is a library which calculates details about various mortgage types (Fixed, ARM, Extra Payments etc). This is not a web interface but pure javascript library which takes input and returns Javascript response objects.

History
=======
While I was researching for my home mortgage, I wanted to do comparative analysis to see what it would look like if I have to refinance/sell after various stages (3 years, 5 years, 7 years etc) to findout which type of mortgage works out well. I couldn't find a good source which helps with that analysis. So I thought about creating a library and develop a page which does it. So this library is result of that thought.

Features
=======
* Fixed Interest Mortgage
* ARM Mortgage with Initial Cap, Periodic Cap, Lifetime Cap and arbitrary (at a month interval) monthly intervals.
* Supports adding any number of extra payments (either one time or at a particular periodic intervals)
* Creates the amortized payment schedule for entire loan term
* Takes down payment as dollar amount or percentage of sale price
* Calculates the roll up summary by to date, loan year and calendar year.
* Supports adding property tax into payment total
* Calculates the total loan cost

Usage
=====

Example
=======

Request
-------
{
      "salePrice":50000,
      "interestRate":5,
      "loanTermMonths":12,
      "propertyTaxRate":0,
      "adjustFixedRateMonths":6,
      "adjustInitialCap":0.25,
      "adjustPeriodicCap":0.25,
      "adjustLifetimeCap":15,
      "startDate":"2014-08-01T00:27:47.788Z",
      "extras":[
         {
            "startMonth":1,
            "endMonth":180,
            "extraIntervalMonths":1,
            "extraAmount":100
         },
         {
            "startMonth":1,
            "endMonth":180,
            "extraIntervalMonths":12,
            "extraAmount":1000
         }
      ]
   }

Response
--------
{
   "loanTermMonths":12,
   "salePrice":50000,
   "interestRate":5,
   "downPayment":"20%",
   "extras":[
      {
         "startMonth":1,
         "endMonth":180,
         "extraIntervalMonths":1,
         "extraAmount":100
      },
      {
         "startMonth":1,
         "endMonth":180,
         "extraIntervalMonths":12,
         "extraAmount":1000
      }
   ],
   "propertyTaxRate":0,
   "homeInsurance":0,
   "adjustFixedRateMonths":6,
   "adjustInitialCap":0.25,
   "adjustPeriodicCap":0.25,
   "adjustLifetimeCap":15,
   "adjustIntervalMonths":12,
   "startDate":"2014-08-01T00:26:09.758Z",
   "loanAmount":40000,
   "totalLoanCost":1047.54,
   "paymentSchedule":[
      {
         "interestRate":5,
         "scheduledMonthlyPayment":3424.3,
         "interest":166.67,
         "principal":3257.63,
         "extra":1100,
         "principalTotal":4357.63,
         "propertyTax":0,
         "paymentTotal":4524.3,
         "paymentDate":"2014-09-01T00:26:09.758Z",
         "remainingLoanBalnce":35642.37,
         "loanMonth":1,
         "loanYear":1,
         "interestLoanYearToDate":166.67,
         "principalLoanYearToDate":3257.63,
         "extraLoanYearToDate":1100,
         "principalTotalLoanYearToDate":4357.63,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":4524.3,
         "interestToDate":166.67,
         "principalToDate":3257.63,
         "extraToDate":1100,
         "principalTotalToDate":4357.63,
         "propertyTaxToDate":0,
         "paymentTotalToDate":4524.3
      },
      {
         "interestRate":5,
         "scheduledMonthlyPayment":3424.3,
         "interest":148.51,
         "principal":3275.79,
         "extra":100,
         "principalTotal":3375.79,
         "propertyTax":0,
         "paymentTotal":3524.3,
         "paymentDate":"2014-10-01T00:26:09.758Z",
         "remainingLoanBalnce":32266.58,
         "loanMonth":2,
         "loanYear":1,
         "interestLoanYearToDate":315.18,
         "principalLoanYearToDate":6533.42,
         "extraLoanYearToDate":1200,
         "principalTotalLoanYearToDate":7733.42,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":8048.6,
         "interestToDate":315.18,
         "principalToDate":6533.42,
         "extraToDate":1200,
         "principalTotalToDate":7733.42,
         "propertyTaxToDate":0,
         "paymentTotalToDate":8048.6
      },
      {
         "interestRate":5,
         "scheduledMonthlyPayment":3424.3,
         "interest":134.44,
         "principal":3289.86,
         "extra":100,
         "principalTotal":3389.86,
         "propertyTax":0,
         "paymentTotal":3524.3,
         "paymentDate":"2014-11-01T00:26:09.758Z",
         "remainingLoanBalnce":28876.72,
         "loanMonth":3,
         "loanYear":1,
         "interestLoanYearToDate":449.62,
         "principalLoanYearToDate":9823.28,
         "extraLoanYearToDate":1300,
         "principalTotalLoanYearToDate":11123.28,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":11572.9,
         "interestToDate":449.62,
         "principalToDate":9823.28,
         "extraToDate":1300,
         "principalTotalToDate":11123.28,
         "propertyTaxToDate":0,
         "paymentTotalToDate":11572.9
      },
      {
         "interestRate":5,
         "scheduledMonthlyPayment":3424.3,
         "interest":120.32,
         "principal":3303.98,
         "extra":100,
         "principalTotal":3403.98,
         "propertyTax":0,
         "paymentTotal":3524.3,
         "paymentDate":"2014-12-01T01:26:09.758Z",
         "remainingLoanBalnce":25472.74,
         "loanMonth":4,
         "loanYear":1,
         "interestLoanYearToDate":569.94,
         "principalLoanYearToDate":13127.26,
         "extraLoanYearToDate":1400,
         "principalTotalLoanYearToDate":14527.26,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":15097.2,
         "interestToDate":569.94,
         "principalToDate":13127.26,
         "extraToDate":1400,
         "principalTotalToDate":14527.26,
         "propertyTaxToDate":0,
         "paymentTotalToDate":15097.2
      },
      {
         "interestRate":5,
         "scheduledMonthlyPayment":3424.3,
         "interest":106.14,
         "principal":3318.16,
         "extra":100,
         "principalTotal":3418.16,
         "propertyTax":0,
         "paymentTotal":3524.3,
         "paymentDate":"2015-01-01T01:26:09.758Z",
         "remainingLoanBalnce":22054.58,
         "loanMonth":5,
         "loanYear":1,
         "interestLoanYearToDate":676.08,
         "principalLoanYearToDate":16445.42,
         "extraLoanYearToDate":1500,
         "principalTotalLoanYearToDate":17945.42,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":18621.5,
         "interestToDate":676.08,
         "principalToDate":16445.42,
         "extraToDate":1500,
         "principalTotalToDate":17945.42,
         "propertyTaxToDate":0,
         "paymentTotalToDate":18621.5
      },
      {
         "interestRate":5,
         "scheduledMonthlyPayment":3424.3,
         "interest":91.89,
         "principal":3332.41,
         "extra":100,
         "principalTotal":3432.41,
         "propertyTax":0,
         "paymentTotal":3524.3,
         "paymentDate":"2015-02-01T01:26:09.758Z",
         "remainingLoanBalnce":18622.18,
         "loanMonth":6,
         "loanYear":1,
         "interestLoanYearToDate":767.97,
         "principalLoanYearToDate":19777.82,
         "extraLoanYearToDate":1600,
         "principalTotalLoanYearToDate":21377.82,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":22145.8,
         "interestToDate":767.97,
         "principalToDate":19777.82,
         "extraToDate":1600,
         "principalTotalToDate":21377.82,
         "propertyTaxToDate":0,
         "paymentTotalToDate":22145.8
      },
      {
         "interestRate":5.25,
         "scheduledMonthlyPayment":3151.39,
         "interest":81.47,
         "principal":3069.92,
         "extra":100,
         "principalTotal":3169.92,
         "propertyTax":0,
         "paymentTotal":3251.39,
         "paymentDate":"2015-03-01T01:26:09.758Z",
         "remainingLoanBalnce":15452.25,
         "loanMonth":7,
         "loanYear":1,
         "interestLoanYearToDate":849.44,
         "principalLoanYearToDate":22847.75,
         "extraLoanYearToDate":1700,
         "principalTotalLoanYearToDate":24547.75,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":25397.19,
         "interestToDate":849.44,
         "principalToDate":22847.75,
         "extraToDate":1700,
         "principalTotalToDate":24547.75,
         "propertyTaxToDate":0,
         "paymentTotalToDate":25397.19
      },
      {
         "interestRate":5.25,
         "scheduledMonthlyPayment":3151.39,
         "interest":67.6,
         "principal":3083.79,
         "extra":100,
         "principalTotal":3183.79,
         "propertyTax":0,
         "paymentTotal":3251.39,
         "paymentDate":"2015-04-01T00:26:09.758Z",
         "remainingLoanBalnce":12268.46,
         "loanMonth":8,
         "loanYear":1,
         "interestLoanYearToDate":917.05,
         "principalLoanYearToDate":25931.54,
         "extraLoanYearToDate":1800,
         "principalTotalLoanYearToDate":27731.54,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":28648.58,
         "interestToDate":917.05,
         "principalToDate":25931.54,
         "extraToDate":1800,
         "principalTotalToDate":27731.54,
         "propertyTaxToDate":0,
         "paymentTotalToDate":28648.58
      },
      {
         "interestRate":5.25,
         "scheduledMonthlyPayment":3151.39,
         "interest":53.67,
         "principal":3097.72,
         "extra":100,
         "principalTotal":3197.72,
         "propertyTax":0,
         "paymentTotal":3251.39,
         "paymentDate":"2015-05-01T00:26:09.758Z",
         "remainingLoanBalnce":9070.74,
         "loanMonth":9,
         "loanYear":1,
         "interestLoanYearToDate":970.72,
         "principalLoanYearToDate":29029.26,
         "extraLoanYearToDate":1900,
         "principalTotalLoanYearToDate":30929.26,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":31899.98,
         "interestToDate":970.72,
         "principalToDate":29029.26,
         "extraToDate":1900,
         "principalTotalToDate":30929.26,
         "propertyTaxToDate":0,
         "paymentTotalToDate":31899.98
      },
      {
         "interestRate":5.25,
         "scheduledMonthlyPayment":3151.39,
         "interest":39.68,
         "principal":3111.71,
         "extra":100,
         "principalTotal":3211.71,
         "propertyTax":0,
         "paymentTotal":3251.39,
         "paymentDate":"2015-06-01T00:26:09.758Z",
         "remainingLoanBalnce":5859.03,
         "loanMonth":10,
         "loanYear":1,
         "interestLoanYearToDate":1010.41,
         "principalLoanYearToDate":32140.97,
         "extraLoanYearToDate":2000,
         "principalTotalLoanYearToDate":34140.97,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":35151.37,
         "interestToDate":1010.41,
         "principalToDate":32140.97,
         "extraToDate":2000,
         "principalTotalToDate":34140.97,
         "propertyTaxToDate":0,
         "paymentTotalToDate":35151.37
      },
      {
         "interestRate":5.25,
         "scheduledMonthlyPayment":3151.39,
         "interest":25.63,
         "principal":3125.76,
         "extra":100,
         "principalTotal":3225.76,
         "propertyTax":0,
         "paymentTotal":3251.39,
         "paymentDate":"2015-07-01T00:26:09.758Z",
         "remainingLoanBalnce":2633.27,
         "loanMonth":11,
         "loanYear":1,
         "interestLoanYearToDate":1036.04,
         "principalLoanYearToDate":35266.73,
         "extraLoanYearToDate":2100,
         "principalTotalLoanYearToDate":37366.73,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":38402.77,
         "interestToDate":1036.04,
         "principalToDate":35266.73,
         "extraToDate":2100,
         "principalTotalToDate":37366.73,
         "propertyTaxToDate":0,
         "paymentTotalToDate":38402.77
      },
      {
         "interestRate":5.25,
         "scheduledMonthlyPayment":3151.39,
         "interest":11.52,
         "principal":2633.27,
         "extra":0,
         "principalTotal":2633.27,
         "propertyTax":0,
         "paymentTotal":2644.79,
         "paymentDate":"2015-08-01T00:26:09.758Z",
         "remainingLoanBalnce":0,
         "loanMonth":12,
         "loanYear":1,
         "interestLoanYearToDate":1047.56,
         "principalLoanYearToDate":37900,
         "extraLoanYearToDate":2100,
         "principalTotalLoanYearToDate":40000,
         "propertyTaxLoanYearToDate":0,
         "paymentTotalLoanYearToDate":41047.56,
         "interestToDate":1047.56,
         "principalToDate":37900,
         "extraToDate":2100,
         "principalTotalToDate":40000,
         "propertyTaxToDate":0,
         "paymentTotalToDate":41047.56
      }
   ],
   "numberOfPayments":12,
   "monthlyPayment":3424.3
}
