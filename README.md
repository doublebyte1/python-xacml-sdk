# README

Run a client that uses the python-xacml-sdk to contact an AuthzForce server.

## Quick Setup

Install sdk:

```
python -m venv python-xacml-sdk
python-xacml-sdk
. bin/activate
git clone https://github.com/doublebyte1/python-xacml-sdk.git
cd python-xacml-sdk
pip install --upgrade pip
pip install -r requirements.txt
```

Create a [configuration file](.pyxacml_sdk/samples/config.yml) for your AuthzForce server and copy it to ```/tmp/pyxacml_sdk``` If you don't have access to a server, you can use this one:

```
docker-compose up -d
```

Create domain:

```
curl -s --request POST \
--header "Accept: application/xml" \
--header "Content-Type: application/xml;charset=UTF-8" \
--data @domainProperties.xml \
 http://localhost:8080/authzforce-ce/domains
```

Retrieve domain:

```
 curl -s --request GET http://localhost:8080/authzforce-ce/domains
```

Run the sample client on this folder:

```
python simple_authz_request.py
```
