# Ransomware e keyloggers: detecção, prevenção e resposta

Estudo documentado para o Bootcamp Santander Cibersegurança do Zero à Prática, da DIO. O trabalho segue a modalidade de documentação de aprendizados prevista no enunciado. Os cenários abaixo são fictícios e servem para exercitar a interpretação de sinais e a escolha de controles. Os resultados descritos são esperados, sem alegação de execução prática.

## Ransomware

Ransomware compromete a disponibilidade dos dados. Um incidente pode deixar arquivos ilegíveis e vir acompanhado de uma exigência de pagamento. Alguns incidentes também envolvem roubo de dados e ameaça de divulgação. A criptografia tem usos legítimos, como proteger backups. No ransomware, ela é usada sem autorização para impedir que a vítima acesse seus próprios arquivos.

### Cenário de análise

Uma equipe relata que vários documentos de um compartilhamento ficaram ilegíveis em poucos minutos. Os registros mostram muitas alterações feitas pela mesma conta e aparece uma mensagem de cobrança.

- **O que observar:** horário e volume das alterações, conta que as realizou, compartilhamentos afetados e alertas do antivírus ou da ferramenta de proteção de endpoints.
- **Como interpretar:** alterações em massa podem ter origem legítima, como uma migração. A combinação com arquivos ilegíveis e uma mensagem de cobrança aumenta a suspeita. Os registros ajudam a delimitar o impacto.
- **Resposta inicial:** acionar a equipe responsável, isolar o equipamento afetado conforme o procedimento de resposta e preservar registros e evidências.
- **Recuperação:** identificar uma cópia íntegra anterior ao incidente, restaurar primeiro em um ambiente limpo e verificar se os arquivos abrem e se o serviço funciona.

## Keylogger

Um keylogger registra o que a pessoa digita. O risco inclui exposição de credenciais, conversas e dados de trabalho. Em um incidente, o programa pode armazenar dados localmente ou transmiti-los. O fato de a máquina continuar funcionando normalmente dificulta perceber o problema pelo uso cotidiano.

### Cenário de análise

A proteção do endpoint sinaliza um programa desconhecido em um computador. No mesmo período, os registros mostram conexões externas incomuns e a equipe recebe um alerta de login suspeito.

- **O que observar:** alertas do endpoint, origem e assinatura do programa, horário das conexões e registros de autenticação.
- **Como interpretar:** um programa desconhecido ou uma conexão externa isolada é só um indício. A coincidência entre eventos ajuda a priorizar a investigação. A captura de teclas e o envio de dados precisam de evidência própria.
- **Resposta inicial:** isolar o equipamento conforme o procedimento de resposta e preservar os registros. Usar um dispositivo confiável para revogar sessões e trocar as credenciais potencialmente expostas.
- **Recuperação:** validar a limpeza ou reinstalação do equipamento, revisar os logins e acompanhar novos alertas antes de devolver a máquina ao uso normal.

## Controles e como verificar

| Controle | Aplicação | Verificação defensiva |
| --- | --- | --- |
| Antivírus e proteção de endpoints | Monitorar processos suspeitos e alterações em arquivos | Confirmar que a proteção está ativa e que os alertas chegam à equipe responsável |
| Firewall e segmentação | Restringir fluxos entre equipamentos e destinos externos conforme a necessidade | Revisar regras e confirmar que conexões esperadas funcionam e que bloqueios aparecem nos registros |
| Sandboxing | Isolar a análise de conteúdo suspeito em ambiente próprio | Conferir as configurações de isolamento e a separação de dados e redes do ambiente de trabalho |
| Backups protegidos | Manter cópias com acesso restrito e versões recuperáveis | Restaurar uma cópia de teste e abrir uma amostra de arquivos para verificar integridade |
| Privilégio mínimo | Limitar o acesso de contas e aplicações a dados e serviços | Revisar permissões e testar o funcionamento com uma conta comum |
| Autenticação multifator | Reduzir o risco do uso indevido de credenciais expostas | Confirmar que o acesso a contas sensíveis exige o segundo fator e que sessões podem ser revogadas |
| Conscientização | Ensinar a reconhecer anexos suspeitos, instalar software de fontes confiáveis e reportar incidentes | Verificar se os usuários conhecem o canal de reporte e sabem quais informações encaminhar |

## Qual ferramenta usar primeiro?

Em suspeita de ransomware, os registros de arquivos, da conta e do endpoint ajudam a identificar o alcance. Os backups entram na fase de recuperação. Em suspeita de keylogger, os registros do endpoint ajudam a investigar o processo, e os de autenticação ajudam a avaliar o possível uso de credenciais. A análise do tráfego pode complementar essa investigação. Capturar pacotes, por si só, não confirma o conteúdo de uma transmissão criptografada.

## Conclusão

Os cenários apresentam prioridades diferentes. No ransomware, é importante conter alterações e planejar uma restauração segura. No keylogger, além de tratar o equipamento, é preciso avaliar a exposição de credenciais e sessões. Em ambos, as evidências orientam a resposta e ajudam a verificar se os controles funcionaram.
