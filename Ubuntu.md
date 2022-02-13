- Enter in root and install easy-rsa

      sudo su -
      apt install easy-rsa
- Copy the folder easy-rsa to etc

      cp -r /usr/share/easy-rsa/ /etc/
- Enter in the folder and open the `openssl` configuration and coment the line of `RANDFILE`
       
      cd /etc/easy-rsa/
      nano openssl-easyrsa.conf
      comentar RANDFILE
- Change vars name and open it

      mv vars.example vars
      nano vars
- Inside change `“ca_only”` to `“org”` and add some information of the enterprise
- To create a certificate do this steps

      ./easyrsa init-pki
      ./easyrsa build-ca nopass #build CA
      ./easyrsa build-server-full www.example.com nopass #build server CA
      ./easyrsa build-server-full www.example2.com nopass #build second server CA
      ./easyrsa build-client-full vpn.example2.com nopass #to second server
      ./easyrsa build-client-full client.cliente.com nopass #to a client
And its done it      
