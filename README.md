# Simulador de Topologia de Rede

Simulador did├ítico (estilo Packet Tracer) para montar topologias, configurar IP e testar comunica├º├úo entre hosts.

## Recursos

- **Dispositivos:** Host, Switch, Roteador, **Servidor DHCP**, **ISP (nuvem Internet)**
- **Cabos e valida├º├╡es:** conflitos de IP, gateway, m├íscaras, loops de switch, rotas, enlaces WAN /30
- **Simula├º├úo de mensagem:** encapsulamento e anima├º├úo no quadro
- **DHCP:** escopo, range, m├íscara, gateway, DNS, lease
- **Renova├º├úo T1:** na metade do lease o host renova automaticamente (REQUEST ΓåÆ ACK animado)
- **ISP:** interliga sites de clientes; **IPs manuais no laborat├│rio**; peering ISPΓåöISP; atalhos /30 opcionais; rotas propagadas pela nuvem
- **Regi├╡es:** quadrados coloridos s├│ para marcar ├íreas no lab (ex.: Norte/Sul) ΓÇö crie com + Regi├úo (clique no quadro), arraste/redimensione e exclua ΓÇö n├úo afetam a rede

## Como usar (GitHub Pages)

Abra o site publicado (ap├│s ativar o Pages) ou o arquivo `index.html` / `simulador-topologia-rede.html` no navegador.

### Atividade DHCP (sugest├úo)

1. Monte a LAN: hosts + switch + roteador + servidor DHCP  
2. Configure o IP do roteador (gateway da LAN)  
3. Ligue o **DHCP no mesmo switch** dos hosts  
4. Configure escopo (range, m├íscara, gateway, DNS, lease)  
5. Nos hosts: modo **DHCP** ΓåÆ **Obter IP**  
6. Para ver a renova├º├úo na aula, use lease curto (ex.: `30` ou `40` segundos)  

### Atividade ISP ΓÇö dois sites pela Internet (sugest├úo)

1. **Site A:** Host(s) + Switch + Roteador (ex.: LAN `192.168.1.0/24`, gateway `192.168.1.1`)  
2. **Site B:** Host(s) + Switch + Roteador (ex.: LAN `192.168.2.0/24`, gateway `192.168.2.1`)  
3. Adicione **+ ISP** e ligue **R1 Γåö ISP** e **R2 Γåö ISP**  
4. **Configure manualmente** os IPs do enlace (mesma sub-rede nos dois lados), ex.:  
   - ISP `PE0/0` = `200.0.0.1` / `255.255.255.252`  
   - R1 WAN = `200.0.0.2` / `255.255.255.252`  
5. Nos hosts: IP + gateway = interface LAN do roteador **local**  
6. **Simular Mensagem** entre sites ΓÇö o pacote passa pela nuvem ISP  
7. (Opcional) No painel do ISP h├í bot├╡es para preencher `/30` automaticamente  

### Peering entre ISPs (dois provedores)

1. Monte Site A em **ISP1** e Site B em **ISP2**  
2. Ligue **ISP1 Γåö ISP2**  
3. Configure o peering **├á m├úo** (ex.: `200.255.0.1` Γåö `200.255.0.2` `/30`)  
4. Sites se alcan├ºam: HostA ΓåÆ R1 ΓåÆ ISP1 ΓåÆ ISP2 ΓåÆ R2 ΓåÆ HostB


## Arquivos

| Arquivo | Descri├º├úo |
|---------|-----------|
| `index.html` | Entrada do site (GitHub Pages) |
| `simulador-topologia-rede.html` | Simulador completo |
| `labs-erros/` | Labs de IP/ISP com erros plantados |
| `labs-seguranca/` | Labs de seguran├ºa b├ísica (importar + auditar) |
| `imgs/` | ├ìcones de switch e roteador |

## Desenvolvimento

Basta abrir o HTML no navegador ΓÇö n├úo precisa de servidor Node para o simulador de topologia.
