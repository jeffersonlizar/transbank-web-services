
python -V
- Python 3.4 debido a que py-wsse tiene soporte hasta Python 3.4

Instalar requirements

pip install -r requirements.txt

Modificacion de librerias

* En la librería suds ubicada en el virtualenv se realiza las siguiente modificacion

    - En el archivo client.py

    modificar:
    result = plugins.message.sending(envelope=soapenv)
    if (result):
        soapenv = result.envelope
    request = Request(location, soapenv)

* En la librería wsse ubicada en el virtualenv se realiza las siguiente modificacion

    - En el archivo signing.py

    comentar:
    _sign_node(ctx, signature, security.find(ns(WSU_NS, 'Timestamp')))

    - En el archivo suds.py

    comentar:
    context.envelope = encrypt(context.envelope, self.their_certfile)
    context.reply = decrypt(context.reply, self.keyfile)


Datos de Prueba ambiente Integración.

VISA CREDIT CARD (WILL BE APPROVED / SERÁ APROBADA)
Number: 4051885600446623 CVV: 123 Year: any / cualquiera Month: any / cualquiera

MASTERCARD CREDIT CARD (WILL BE DENIED / SERÁ DENEGADA)
Number: 5186059559590568 CVV: 123 Year: any / cualquiera Month: any / cualquiera

BANK VIEW
RUT: 11.111.111-1 Password: 123