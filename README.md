# Debug

1. Clone the repo
2. Install dependencies
3. Run strapi

!! The database is included with example data, use that !!

## Credentials:
admin@admin.com

Admin1234

## Try to use this query

```
query Offerings {
  offerings(
    where: {
      _where: [
        {
          attribute_list: {
            value: "Vegan",
            attribute_type: {
            	key: "diet"
            }
          }
        },
        {
          attribute_list: {
            value: "Squared",
            attribute_type: {
            	key: "layout"
            }
          }
        }
      ]
    }
  ) {
    id
    name
    attribute_list {
      id
      value
      attribute_type {
        id
        name
        key
      }
    }
  }
}
```
### What is expected?
The query should return ONE result, Foodtruck one

### What is happening instead?
Zero results are returned