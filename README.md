🌊 Olho no Mar — Sistema Operacional de Comando e Alerta SOS Litorâneo
​Sistema web em tempo real desenvolvido para operações de salvamento aquático, conectando Guarda-Vidas na orla diretamente à Central de Comando com alerta sonoro imediato, georreferenciamento tático e controle exclusivo de postos por turno.
​🌐 Aplicação em Produção: https://olho-no-mar.vercel.app
​📋 Principais Funcionalidades
​1. Módulo do Guarda-Vidas (Campo / Mobile)
​Acesso Individual: Cada agente possui login, matrícula e senha próprios cadastrados pela Central.
​Check-in Exclusivo de Posto: Ao entrar no sistema, o guarda-vidas seleciona o posto onde vai atuar no turno.
​Bloqueio de Duplicidade (Posto & Coordenadas): O sistema impede automaticamente que dois agentes assumam o mesmo posto ou operem nas mesmas coordenadas GPS (raio < 25\text{ m} ou coordenada exata), exibindo quem já está ativo no local.
​Botão SOS de Acionamento Rápido: Disparo em um toque com seleção opcional da natureza da ocorrência (Afogamento / Resgate, Apoio Médico, Embarcação, Busca na Orla), vibração tátil e retorno visual imediato quando a Central confirma ciência (ACK).
​Encerramento / Troca de Turno: Ao final do expediente, o agente libera o posto para o próximo colega.
​2. Módulo da Central de Comando (Despacho & Monitoramento)
​Sirene Sonora de Alta Prioridade (Yelp / Hi-Lo): Sintetizada nativamente via Web Audio API, dispara automaticamente ao receber um alerta SOS não confirmado e cessa somente após o operador clicar em Confirmar (ACK) ou encerrar a ocorrência.
​Mapa Tático Interativo (Leaflet): Visualização em tempo real dos postos livres (azul), postos ocupados em serviço (verde) e alertas SOS ativos com pino pulsante (vermelho). Permite arrastar marcadores de postos para ajuste fino de coordenadas.
​Gestão de Efetivo e Postos: Cadastro individual de agentes, bloqueio/desbloqueio de acessos, cadastro de postos com coordenadas exclusivas e liberação forçada de turnos.
​Auditoria e Relatórios: Histórico de atendimentos encerrados e exportação de ocorrências em formato CSV.
​3. Arquitetura Resiliente & Hardware
​CSS 100% Embutido (Zero Dependência de CDN de Estilo): Interface autônoma carregada instantaneamente mesmo sob oscilação de sinal 4G/5G na faixa de areia.
​Integração Hardware ESP32 + LoRa 915 MHz: Compatível com botoeiras físicas de emergência instaladas em postos sem cobertura de celular, enviando alertas via gateway LoRa diretamente para a API REST do sistema.
