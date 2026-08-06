# Gabarito — Labs de Segurança (somente professor)

## 01 — Rede insegura

Corrigir em cada dispositivo (Salvar configuração) e reauditar:

### HostA / HostB
- Senha forte (ex.: `HostA#2026x`)
- Atualizações: **ligado**
- Firewall: **ligado**
- Permitir Wi-Fi públicas: **desligado**

### R1
- Senha admin forte (ex.: `Router#Admin99`)
- Atualizações: **ligado**
- Firewall: **ligado**
- Admin remota: **desligada** (ou aceitar aviso amarelo)
- Wi-Fi: WPA2 ou WPA3 + senha forte (ou desligar Wi-Fi se for só cabo)

## 02 — Wi-Fi obsoleto

### R-WiFi
- Protocolo: **WPA2** ou **WPA3**
- Senha Wi-Fi forte (não `12345678`, não WEP)

Notebook e demais itens já vêm seguros.

## 03 — Hosts desprotegidos

### PC-Aluno1 e PC-Aluno2
- Senha forte
- Atualizações on
- Firewall on
- Wi-Fi pública off

R-Lab já está seguro.

## 04 — Duas redes + invasão (firewall)

Topologia: **Site A** (`192.168.1.0/24`) e **Site B** (`192.168.2.0/24`) via **ISP**.

| Enlace | IPs |
|--------|-----|
| R-A WAN ↔ ISP | `200.0.0.2` ↔ `200.0.0.1` `/30` |
| R-B WAN ↔ ISP | `200.0.1.2` ↔ `200.0.1.1` `/30` |

### Fase 1 — invasão bem-sucedida
- `PC-SiteA` e `PC-SiteB` vêm com **firewall OFF** e arquivo secreto.
- **🎯 Teste de invasão** em qualquer um → professor **lê o arquivo** (vermelho).
- Mensagem esperada: rede falhou / arquivo obtido.

### Fase 2 — proteção
Em **PC-SiteA** e **PC-SiteB**:
- ☑ **Firewall do host ativo**
- Salvar configuração

Opcional (auditoria completa):
- Em **R-A** e **R-B**: firewall do roteador **ligado**

### Fase 3 — reteste
- Mesmo **🎯 Teste de invasão** → **bloqueado** (verde).
- Painel do host: aviso de breach some ao salvar com firewall ON.
- **🔒 Segurança** sem falha de “firewall desativado” nesses hosts.
