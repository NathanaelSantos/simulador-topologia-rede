# Simulador de Topologia de Rede

Simulador didático (estilo Packet Tracer) para montar topologias, configurar IP e testar comunicação entre hosts.

## Recursos

- **Dispositivos:** Host, Switch, Roteador, **Servidor DHCP**, **ISP (nuvem Internet)**
- **Cabos e validações:** conflitos de IP, gateway, máscaras, loops de switch, rotas, enlaces WAN /30
- **Simulação de mensagem:** encapsulamento e animação no quadro
- **DHCP:** escopo, range, máscara, gateway, DNS, lease
- **Renovação T1:** na metade do lease o host renova automaticamente (REQUEST → ACK animado)
- **ISP:** interliga sites de clientes; **IPs manuais no laboratório**; peering ISP↔ISP; atalhos /30 opcionais; rotas propagadas pela nuvem
- **Regiões:** quadrados coloridos só para marcar áreas no lab (ex.: Norte/Sul) — crie com + Região (clique no quadro), arraste/redimensione e exclua — não afetam a rede
- **🔒 Segurança básica:** auditoria de senhas, Wi-Fi (WPA/WPA2/WPA3), firewall, atualizações, Wi-Fi públicas e proteção dos equipamentos — falhas em **vermelho**

## Como usar (GitHub Pages)

Abra o site publicado (após ativar o Pages) ou o arquivo `index.html` / `simulador-topologia-rede.html` no navegador.

### Atividade DHCP (sugestão)

1. Monte a LAN: hosts + switch + roteador + servidor DHCP  
2. Configure o IP do roteador (gateway da LAN)  
3. Ligue o **DHCP no mesmo switch** dos hosts  
4. Configure escopo (range, máscara, gateway, DNS, lease)  
5. Nos hosts: modo **DHCP** → **Obter IP**  
6. Para ver a renovação na aula, use lease curto (ex.: `30` ou `40` segundos)  

### Atividade ISP — dois sites pela Internet (sugestão)

1. **Site A:** Host(s) + Switch + Roteador (ex.: LAN `192.168.1.0/24`, gateway `192.168.1.1`)  
2. **Site B:** Host(s) + Switch + Roteador (ex.: LAN `192.168.2.0/24`, gateway `192.168.2.1`)  
3. Adicione **+ ISP** e ligue **R1 ↔ ISP** e **R2 ↔ ISP**  
4. **Configure manualmente** os IPs do enlace (mesma sub-rede nos dois lados), ex.:  
   - ISP `PE0/0` = `200.0.0.1` / `255.255.255.252`  
   - R1 WAN = `200.0.0.2` / `255.255.255.252`  
5. Nos hosts: IP + gateway = interface LAN do roteador **local**  
6. **Simular Mensagem** entre sites — o pacote passa pela nuvem ISP  
7. (Opcional) No painel do ISP há botões para preencher `/30` automaticamente  

### Peering entre ISPs (dois provedores)

1. Monte Site A em **ISP1** e Site B em **ISP2**  
2. Ligue **ISP1 ↔ ISP2**  
3. Configure o peering **à mão** (ex.: `200.255.0.1` ↔ `200.255.0.2` `/30`)  
4. Sites se alcançam: HostA → R1 → ISP1 → ISP2 → R2 → HostB

### Atividade Segurança básica (fluxo de aula)

**Professor:** envia um JSON de [`labs-seguranca/`](./labs-seguranca/) (falhas plantadas) ou a topologia da turma.

**Aluno:**

1. Abre o simulador → **⬆ Importar** o arquivo  
2. A auditoria de segurança roda **automaticamente**  
3. Se falhar: itens em **vermelho** + dispositivos destacados  
4. Corrige o bloco **🔒 Segurança** em Host/Roteador → **Salvar**  
5. Clica em **🔒 Segurança** / **Auditar** de novo  
6. Quando aparecer **✅ REDE SEGURA**, exporta **⬇ Relatório** e entrega o JSON  

| Resultado | Significado |
|-----------|-------------|
| **OK / REDE SEGURA** | Rede planejada passou no checklist básico |
| **Falhas em vermelho** | Lista cada problema (senha, Wi-Fi, WPA, updates, firewall…) |

Checklist: senhas, Wi-Fi, WPA/WPA2/WPA3, atualizações, firewall, Wi-Fi pública, proteção dos equipamentos.

### Gancho: arquivo secreto → teste de invasão → firewall

1. No **Host**, o aluno cria um **arquivo secreto** (nome + conteúdo) e salva  
2. Professor: **🎯 Teste de invasão** → escolhe o PC → tenta obter o arquivo  
3. **Firewall OFF** = professor lê o arquivo = **rede falhou** (vermelho)  
4. Aluno liga o **firewall do host** e retesta = ataque bloqueado (verde)  
5. Aí você entra na teoria de **firewall** (e depois no roteador)

## Arquivos

| Arquivo | Descrição |
|---------|-----------|
| `index.html` | Entrada do site (GitHub Pages) |
| `simulador-topologia-rede.html` | Simulador completo |
| `labs-erros/` | Labs de IP/ISP com erros plantados |
| `labs-seguranca/` | Labs de segurança básica (importar + auditar) |
| `imgs/` | Ícones de switch e roteador |

## Desenvolvimento

Basta abrir o HTML no navegador — não precisa de servidor Node para o simulador de topologia.
