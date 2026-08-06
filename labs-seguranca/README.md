# Labs de Segurança Básica

Arquivos JSON para importar no **Simulador de Topologia de Rede**.  
Cada lab planta **falhas de segurança** (senhas, Wi-Fi, firewall, atualizações) para a turma diagnosticar e corrigir.

## Como o aluno usa

1. Abra o simulador (`simulador-topologia-rede.html`).
2. Clique em **⬆ Importar** e escolha um arquivo desta pasta.
3. Clique em **🔒 Segurança** (ou **Auditar** no painel lateral).
4. Corrija as falhas em **vermelho** nos dispositivos (painel de propriedades → bloco 🔒 Segurança).
5. Clique de novo em **🔒 Segurança** até o badge ficar **OK**.

### Gancho de aula: arquivo secreto + teste de invasão

1. No **Host (PC)**, o aluno cria um **arquivo secreto** (nome + conteúdo) e **Salva**.
2. O professor clica em **🎯 Teste de invasão**, escolhe o host e tenta obter o arquivo.
3. **Firewall OFF** → professor lê o arquivo → **rede falhou** (vermelho).
4. Aluno liga o **firewall do host**, salva, reteste → ataque bloqueado (verde).
5. Aí entra a explicação formal de **firewall** (e depois firewall no roteador).

> Entregue só os JSON + este README. O gabarito fica com o professor (`gabarito/`).

## Checklist (segurança básica)

| Tema | O que o auditor exige |
|------|------------------------|
| **Senhas seguras** | ≥ 8 caracteres, letras + números; sem senhas comuns (`admin`, `123456`…) |
| **Proteção do Wi-Fi** | Se o Wi-Fi estiver ligado: senha forte |
| **WPA / WPA2 / WPA3** | Aberto e WEP = falha; WPA = aviso; WPA2/WPA3 = ok |
| **Atualização** | Hosts e roteadores com atualizações ativas |
| **Firewall** | Firewall do host e do roteador ativos |
| **Wi-Fi públicas** | Host **não** deve permitir redes Wi-Fi públicas |
| **Proteção dos equipamentos** | Senha forte de admin no roteador; admin remota com cuidado |

## Labs

| Arquivo | Tema | Dificuldade |
|---------|------|-------------|
| `01-rede-insegura.json` | Várias falhas de uma vez (senhas, Wi-Fi aberto, firewall off…) | ★★☆ |
| `02-wifi-obsoleto.json` | Wi-Fi com WEP e senha fraca | ★☆☆ |
| `03-hosts-desprotegidos.json` | Hosts sem senha, sem firewall, Wi-Fi pública liberada | ★☆☆ |

## Sugestão de aula (40–50 min)

1. **10 min** — Revisar os 7 tópicos de segurança básica  
2. **15 min** — Lab 01 (dupla): importar → auditar → corrigir  
3. **10 min** — Lab 02 ou 03  
4. **5 min** — Exportar a topologia “segura” e entregar o JSON  

## Critério de sucesso

- Painel **Segurança** com badge **OK** (sem falhas vermelhas)  
- Avisos amarelos (ex.: admin remota ligada) podem ser aceitos se o professor permitir  
- Validação de IP (✔ Validar) também deve estar consistente se a topologia tiver endereçamento
