# RDO-decrypt

The following code can decrypt BinaryFormatter serialized data stored in Data/Connections.dat

```
def decrypt_password(input):
    key  = bytes.fromhex('D958C41E911C10871E65FFC0CAE3B6070E5E49F6D20C7B9B18AD2F07CAA3069C')
    iv   = bytes.fromhex('1E65FFC0CAE3B607648C977AC1D6C3DF')

    aes  = AES.new(key, AES.MODE_CBC, iv)
    data = aes.decrypt(bytes.fromhex(input))
    return data.decode('utf-8').strip()
```
