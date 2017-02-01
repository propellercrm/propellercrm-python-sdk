# Propeller CRM Python SDK

[Propeller](https://www.propellercrm.com) is the CRM salespeople actually want to use. And it's also pretty great for developers!

## Installation

~~~
pip install propellercrm
~~~

## Usage

~~~
import propellercrm
~~~

### Authorization

~~~
propellercrm.user = '<email>'
propellercrm.api_key = '<key>'
~~~

### Get a list of leads

~~~
leads = propellercrm.Lead.list()
~~~

### Get a filtered list of leads

~~~
filtered_list = propellercrm.Lead.list(first_name__startswith='c')
~~~

### Get an ordered list of leads

~~~
filtered_list = propellercrm.Lead.list(order_by='first_name')
~~~

### Get the first and then second page of leads

~~~
page_1 = propellercrm.Lead.list(limit=20)
page_2 = propellercrm.Lead.list(offset=20, limit=20)
~~~

### Iterate through all matching leads

This iterator automatically handles pagination calls

~~~
for lead in propellercrm.Lead.list(first_name__startswith='c', order_by='first_name'):
    print lead
~~~

### Get a contact

~~~
contact = propellercrm.Contact.get('<id>')
~~~

### Access contact attributes

~~~
print contact.first_name
print contact.customYourCustomAttr
~~~

### Get a contact and related account

~~~
contact = propellercrm.Contact.get('<id>', expand=['account'])
print contact.account.name
~~~

### Create a contact

~~~
new_contact = propellercrm.Contact.create(first_name='John', last_name='Smith')
~~~

### Update a contact

~~~
contact = propellercrm.Contact.update('<id>', first_name='New Name')
~~~

### Delete a contact

~~~
propellercrm.Contact.delete('<id>')
~~~

## Support

If you have any issues you can contact us at [support@propellercrm.com](mailto:support@propellercrm.com)
