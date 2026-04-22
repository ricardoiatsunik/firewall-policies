# Políticas de Firewall #
Políticas de Firewall são conjuntos de regras usadas para controlar qual tráfego de rede é aceito e, se for aceito, como será processado.

### Correspondendo Tráfego de Rede em Políticas de Firewall ###
O tráfego de rede pode corresponder a critérios, que podemos definir:

<img width="464" height="236" alt="image" src="https://github.com/user-attachments/assets/19b8cea9-2941-414f-8ba6-ae54595558fa" />
<br>
Os campos Source e Destination de uma política de firewall podem ser IP Subnet ou Internet Services.

##

# IP Subnet
<br>
<img width="819" height="357" alt="image" src="https://github.com/user-attachments/assets/2634e9b0-5932-4f7e-9ff6-a2c3d394c6ea" />
<br>
* Para usar um IP Subnet como Source ou Destination, criar um endereço de firewall que corresponda ao IP Subnet.
<br>
* Para criar uma política que permita usuários internos acessarem a Internet, configurar um endereço de firewall que corresponda ao IP Subnet da rede interna e usar como Source.


## 
Também é possível criar um endereço de firewall para um dispositivo em específico, como um Servidor Web, usando o endereço de firewall como Destination em qualquer política de firewall que você queira permitir acesso ao Servidor:
<br>
<br>
<img width="868" height="393" alt="image" src="https://github.com/user-attachments/assets/48839f5b-e380-4720-8f44-63620717c428" />

##

# Internet Services #
Para usar Internet Services como Source ou Destination, selecionar o IS na ISDB (Internet Service Data Base). Um administrador de Fortigate também pode customizar um Internet Service:

<img width="874" height="393" alt="image" src="https://github.com/user-attachments/assets/cc1d50e2-79a1-4c57-8b24-97e3a4bbf2a5" />
<br>
<br>

## Fortigate Policy Table ##

O Fortigate Policy Table contém todas as políticas de firewall. O firewall sempre checa a lista por ordem (de cima pra baixo) e aplica a primeira que conceder, caso contrário desce até o Deny e é negado.
<br>
Isso quer dizer que se deve manter as políticas mais específicas por primeiro:
<br>
<br>
<img width="909" height="493" alt="image" src="https://github.com/user-attachments/assets/6b483f13-8abd-419e-8733-b95a8fa735ee" />

##

# Tráfego Aceito #
Após aceitar o tráfego o Fortigate também pode escanear e filtrar se a política de firewall estiver configurada para isso, bloqueando tráfego malicioso:

<img width="1022" height="500" alt="image" src="https://github.com/user-attachments/assets/346ccfe6-22a3-4969-98c4-99c2cfe8425f" />

# Modos de Inspeção #
Quando se configura uma política de firewall, deve-se selecionar um dos seguintes modos de inspeção:

## Flow-Based Inspection ##
Examina o tráfego conforme passa pelo FortiGate, sem nenhum buffering:
<img width="1123" height="518" alt="image" src="https://github.com/user-attachments/assets/87d35d58-35f0-4d6f-bd83-8379134ce036" />

## Proxy-Based Inspection ##
Na Inspeção Baseada em Proxy, o FortiGate usa buffering e examina o tráfego como um todo, até mesmo em dados que o Flow-Based não inspeciona, porém aumenta a latência da velocidade de transmissão:
<img width="1070" height="480" alt="image" src="https://github.com/user-attachments/assets/b17bd4e3-7844-4651-a357-9552c4910f79" />

# Referência
NSE 3 | Fortinet


