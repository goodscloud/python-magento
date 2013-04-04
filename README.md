Python Magento
==============

Python library to connect to Magento's API.

Examples
--------

    import magento

    url = 'http://domain.com/'
    apiuser = 'user'
    apipass = 'password'

    with magento.Product(url, apiuser, apipass) as product_api:
        ofilter = {'created_at':{'from':'2011-09-15 00:00:00'}}
        products = product_api.list(ofilter)

    with magento.ProductTypes(url, apiuser, apipass) as product_type_api:
        product_type = product_type_api.list()

    with magento.Product(url, apiuser, apipass) as product_api:
        sku = 'prod1'
        product = product_api.info(sku)

    with magento.Order(url, apiuser, apipass) as order_api:
        order_increment_id = '100000001 '
        status = 'canceled'
        order_api.addcomment(order_increment_id, status)
