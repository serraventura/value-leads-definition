# value-leads-definition

### **User Story:**

**As** a Product Owner,  
**I want** the value of leads to be defined based on the quality of the data and market dynamics,  
**So that** we can adjust lead prices fairly and effectively, ensuring that lead values reflect their true worth and align with market conditions.

---

### **Acceptance Criteria:**

1. **Initial Lead Values:**
   - **Full Details with at Least One Document Photo:** Example base value = R$250
   - **Full Details with More Than One Document Provided:** Example base value = R$220
   - **Full Details with at Least One Document Provided:** Example base value = R$200
   - **Full Details:** Example base value = R$180
   - **Intermediate Details:** Example base value = R$100
   - **Minimal Details:** Example base value = R$50
   - **Credit Restrictions: Free:** Example base value = R$0

2. **Supply and Demand Rule:**
   - **Number of Leads and Agents:**
     - If the number of leads is greater than the number of agents, reduce the lead values.
     - If the number of agents is greater than the number of leads, increase the lead values.

   - **Example Adjustment:**
     - If there are 100 leads and 50 agents, and the supply/demand rule dictates a 10% reduction:
       - **Full Details with at Least One Document Photo:** Adjusted value = R$250 * (1 - 0.10) = R$225
       - **Full Details with More Than One Document Provided:** Adjusted value = R$220 * (1 - 0.10) = R$198
       - **Full Details with at Least One Document Provided:** Adjusted value = R$200 * (1 - 0.10) = R$180
       - **Full Details:** Adjusted value = R$180 * (1 - 0.10) = R$162
       - **Intermediate Details:** Adjusted value = R$100 * (1 - 0.10) = R$90
       - **Minimal Details:** Adjusted value = R$50 * (1 - 0.10) = R$45
       - **Credit Restrictions: Free:** Adjusted value = R$0


### **Category Definitions**

For every category "Full Details" will mean: `userIncome, userDeposit, familyIncome, familyArrangement, regionsOfInterest, civilStatus, employmentStatus, userIncomeType and userDependents`.

#### Full Details with at Least One Document Photo (value: 250)

 - **Required Fields**: All "Full Details" + At least one document photo attached.

#### Full Details with More Than One Document Provided (value: 220)

 - **Required Fields**: All "Full Details" + "cpf" by text + plus one document attached.

#### Full Details with at Least One Document Provided (value: 200)

 - **Required Fields**: All "Full Details" + "cpf" by text

#### Full Details (value: 180)

 - **Required Fields**: All "Full Details" + no documents required.

#### Intermediate Details (value: 100)

 - **Required Fields:**
At least the following fields: `userIncome or familyIncome, civilStatus, employmentStatus, userIncomeType, and regionsOfInterest`.

#### Minimal Details (value: 50)

 - **Required Fields:** At least one of the "Full Details" fields.

#### Credit Restrictions (value: 0)
> To be defined

## Data examples:

```
{
   "data":[
      {
         "id":"lead1",
         "fullName":"Carlos Souza",
         "createdAt":"2024-09-01T12:00:00Z",
         "userIncome":"R$6,000",
         "userDeposit":"R$15,000",
         "familyIncome":"R$8,000",
         "familyArrangement":"casado",
         "userNeighborhood":"zona sul",
         "userRegion":"zona_sul",
         "cpf":"123.456.789-00",
         "civilStatus":"casado(a)",
         "employmentStatus":"empregado",
         "userIncomeType":"carteira assinada",
         "userDependents":"2 filhos(as)",
         "hasDocumentAttached":false,
         "hasCpfDocumentAttached":false,
         "hasPayslipDocumentAttached":false,
         "hasBankStatementDocumentAttached":false,
         "leadValue":200
      },
      {
         "id":"lead2",
         "fullName":"Ana Silva",
         "createdAt":"2024-09-10T10:45:00Z",
         "userIncome":"R$4,000",
         "userDeposit":"R$10,000",
         "familyIncome":null,
         "familyArrangement":null,
         "userNeighborhood":"zona norte",
         "userRegion":"zona_norte",
         "cpf":null,
         "civilStatus":"solteiro(a)",
         "employmentStatus":"empregado",
         "userIncomeType":"autonomo",
         "userDependents":"nao possui dependentes",
         "hasDocumentAttached":false,
         "hasCpfDocumentAttached":false,
         "hasPayslipDocumentAttached":false,
         "hasBankStatementDocumentAttached":false,
         "leadValue":100
      }
   ]
}
```

```
{
  "marketAdjustment": 10,
  "leadValues": [
    {
      "category": "Full Details with at Least One Document Photo",
      "code": "FULL_DETAILS_DOC_PHOTO",
      "value": 250
    },
    {
      "category": "Full Details with More Than One Document Provided",
      "code": "FULL_DETAILS_MULTIPLE_DOCS",
      "value": 220
    },
    {
      "category": "Full Details with at Least One Document Provided",
      "code": "FULL_DETAILS_SINGLE_DOC",
      "value": 200
    },
    {
      "category": "Full Details",
      "code": "FULL_DETAILS",
      "value": 180
    },
    {
      "category": "Intermediate Details",
      "code": "INTERMEDIATE_DETAILS",
      "value": 100
    },
    {
      "category": "Minimal Details",
      "code": "MINIMAL_DETAILS",
      "value": 50
    },
    {
      "category": "Credit Restrictions",
      "code": "CREDIT_FREE",
      "value": 0
    }
  ]
}

```

