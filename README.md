# Kash API Python Client

This is the KASH API client for the the Server facing API.

Create a client connected to the test environment:
    from kash import SecretClient

    sk = '<secret key>'
    customerId = '<customer id>'
    sc = SecretClient(secretKey=sk, test=True)

Create an an authorization for payment:

    try:
        authorizationDict = sc.createAuthorization(customerId, '2000')
        authorizationId = authorizationDict['authorization_id']
    except e:
        print e

Clear an authorization:

    try:
        sc.removeAuthorization(authorizationId)
    except e:
        print e

Create a transaction:

    try:
        authorizationDict = sc.createAuthorization(customerId, '2000')
        authorizationId = authorizationDict['authorization_id']
    except e:
        print e
    
    