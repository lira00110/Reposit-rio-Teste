# 🌐 Escopo de Endereçamento Lógico (VLANs)

Como esta documentação possui muitas informações técnicas, clique em cada VLAN abaixo para expandir os detalhes:

<details>
<summary><b>🟢 VLAN 10: Gerenciamento (Switches, APs e Controladora)</b></summary>

* **Faixa de IP:** 192.168.10.X
* **Máscara:** 255.255.255.0 (/24)
* **Gateway (IP do FortiGate):** 192.168.10.1
* **Aplicação:** Exclusiva para os IPs dos 3 switches Ubiquiti, dos 11 Access Points e da Cloud Key Gen2 Plus. Nenhum usuário comum ou máquina industrial entra aqui.
</details>

<details>
<summary><b>🔴 VLAN 20: Produção e Logística (Coletores e Balanças) — Crítica</b></summary>

* **Faixa de IP:** 192.168.20.X
* **Máscara:** 255.255.255.0 (/24)
* **Gateway (IP do FortiGate):** 192.168.20.1
* **Aplicação:** Onde vão rodar os coletores de dados portáteis do almoxarifado, tablets de processo e balanças integradas. Essa rede tem prioridade de tráfego (QoS) configurada no FortiGate para nunca travar o Sankhya.
</details>

<details>
<summary><b>🔵 VLAN 30: Administrativo e Escritórios (Pontos Fixos)</b></summary>

* **Faixa de IP:** 192.168.30.X
* **Máscara:** 255.255.255.0 (/24)
* **Gateway (IP do FortiGate):** 192.168.30.1
* **Aplicação:** Atende a maioria dos 70 pontos fixos solicitados pelo cliente (computadores do RH, Faturamento, Compras, Diretoria e Laboratórios).
</details>

<details>
<summary><b>🟡 VLAN 40: Automação e IoT (Impressoras Térmicas e Relógios de Ponto)</b></summary>

* **Faixa de IP:** 192.168.40.X
* **Máscara:** 255.255.255.0 (/24)
* **Gateway (IP do FortiGate):** 192.168.40.1
* **Aplicação:** Impressoras térmicas Zebra da expedição, câmeras de segurança (CFTV) e leitores de ponto. Dispositivos IoT costumam gerar muito tráfego de broadcast e devem ficar isolados para não lentificar os PCs administrativos.
</details>

<details>
<summary><b>⚪ VLAN 50: Visitantes / Guest (Wi-Fi Administrativo Isolado)</b></summary>

* **Faixa de IP:** 172.16.50.X *(Mudança de classe para fácil identificação visual no firewall)*
* **Máscara:** 255.255.255.0 (/24)
* **Gateway (IP do FortiGate):** 172.16.50.1
* **Aplicação:** Wi-Fi aberto para clientes, fornecedores e celulares pessoais de funcionários.
</details>
