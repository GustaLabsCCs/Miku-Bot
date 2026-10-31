# Política de Privacidade — Miku Bot

**Versão:** 1.0  
**Última atualização:** 31 de outubro de 2026  
**Responsável pelo tratamento:** GustavoLabsCCs  
**Contato sobre privacidade:** gustavodiastrabalhos@gmail.com

## 1. Introdução

A Miku Bot é uma assistente inteligente para Discord, desenvolvida para auxiliar usuários na organização e administração de comunidades, além de oferecer funcionalidades de conversa com inteligência artificial.

Esta Política de Privacidade explica quais informações podem ser processadas durante o uso da Miku, para quais finalidades são utilizadas, onde são armazenadas e como os usuários podem solicitar informações ou exclusão de seus dados.

Esta política se aplica à versão 0.3 Beta e poderá ser atualizada conforme novas funcionalidades forem desenvolvidas.

## 2. Informações processadas

Dependendo dos comandos utilizados, a Miku poderá processar as seguintes informações:

### 2.1. Identificadores do Discord

- ID do usuário que executou um comando.
- ID do servidor em que o comando foi utilizado.
- ID do canal em que ocorreu a interação.
- IDs de servidores e canais relacionados a operações administrativas.

Esses identificadores são utilizados para associar conversas, verificar permissões e executar funcionalidades solicitadas.

### 2.2. Conteúdo das conversas com a IA

Quando alguém utiliza os comandos de inteligência artificial, a Miku pode processar:

- Mensagens enviadas pelo usuário ao comando de IA.
- Respostas produzidas pela Miku.
- Mensagens anteriores utilizadas como contexto.
- Resumos automáticos de conversas anteriores.

A Miku não foi implementada para utilizar todas as mensagens comuns de um servidor como histórico de conversa. No modo de comandos por prefixo, o conteúdo é tratado como comando quando corresponde ao prefixo configurado ou à menção do bot.

### 2.3. Informações sobre servidores

Ao utilizar funcionalidades administrativas, a Miku pode consultar informações necessárias para executar a solicitação, como:

- Nome do servidor e quantidade de membros.
- Quantidade de canais e cargos.
- Nomes, categorias e tipos de canais.
- Nomes e características dos cargos.
- Identificadores necessários para reconhecer recursos do servidor.

Na análise de um servidor de referência, a Miku utiliza informações de canais públicos, como nomes, categorias e tipos. Essa funcionalidade não foi implementada para ler mensagens ou copiar cargos e dados privados do servidor de referência.

### 2.4. Planos administrativos

Quando um usuário solicita a criação ou organização de uma estrutura, a Miku pode armazenar temporariamente ou manter no registro local:

- Identificador do servidor e do usuário responsável.
- Identificadores do canal e da mensagem de origem.
- Pedido original enviado à Miku.
- Estrutura sugerida pela inteligência artificial.
- Resultado da revisão e do processo de execução.
- Informações necessárias para retomar ou cancelar uma operação.

### 2.5. Registros técnicos

A Miku mantém registros técnicos de funcionamento, que podem conter:

- Data e horário dos eventos.
- Comandos utilizados.
- IDs de usuários, servidores e canais.
- Provedor e modelo de inteligência artificial utilizados.
- Informações de diagnóstico, avisos e erros.

Os registros técnicos não são destinados a armazenar deliberadamente o conteúdo integral das conversas, mas mensagens de erro e informações operacionais podem conter dados relacionados a uma interação.

## 3. Uso das informações

As informações processadas podem ser utilizadas para:

- Responder a solicitações enviadas à Miku.
- Manter contexto entre interações com a inteligência artificial.
- Resumir conversas antigas para preservar contexto.
- Analisar estruturas de servidores e elaborar recomendações.
- Criar propostas de categorias, canais e cargos.
- Verificar permissões e autorizações administrativas.
- Executar operações aprovadas explicitamente pelo usuário.
- Prevenir uso excessivo, diagnosticar falhas e manter o funcionamento do bot.

A Miku não possui funcionalidades destinadas à venda de informações pessoais ou à utilização dos dados dos usuários para publicidade direcionada.

## 4. Compartilhamento com provedores de inteligência artificial

A Miku utiliza provedores de inteligência artificial para gerar respostas e elaborar propostas administrativas.

O código suporta serviços como:

- OpenRouter.
- Google Gemini.
- Groq.
- OpenAI.
- Anthropic.
- Ollama.
- Serviços compatíveis com a API da OpenAI, incluindo endpoints configurados pelo operador.

O provedor principal e os provedores alternativos dependem da configuração da instância da Miku. A configuração padrão utiliza OpenRouter e prevê Google e Groq como alternativas, quando suas credenciais estão disponíveis e as condições de fallback são atendidas.

Quando uma solicitação é encaminhada a um provedor externo, podem ser enviados o texto do pedido, o contexto relevante da conversa, instruções necessárias para a geração e, em funcionalidades administrativas, os dados de estrutura do servidor necessários à operação.

O provedor poderá processar essas informações conforme seus próprios termos, políticas de privacidade e configurações de tratamento de dados.

Quando Ollama é utilizado em uma instalação local, o processamento pode ocorrer no ambiente do próprio operador. A localização efetiva depende do endereço configurado para o serviço.

A Miku não possui funcionalidade própria para treinar ou ajustar modelos de inteligência artificial utilizando mensagens dos usuários. Isso não representa uma garantia sobre as práticas de retenção ou utilização de dados dos provedores externos, que devem ser consultadas separadamente.

## 5. Armazenamento e conservação

Os dados persistidos pela implementação analisada são armazenados em arquivos locais no ambiente em que a instância da Miku está sendo executada.

### 5.1. Histórico de conversas

O histórico é separado por servidor, canal e usuário.

Na configuração padrão, são mantidos até 12 turnos de conversa, correspondentes a até 24 mensagens. Quando o histórico ultrapassa o limite de compactação configurado, mensagens antigas podem ser substituídas por um resumo de contexto.

O histórico não possui prazo automático de exclusão por tempo.

O comando `/limpar` permite apagar o histórico de IA associado ao usuário que executou o comando naquele canal e servidor.

### 5.2. Planos administrativos

As propostas possuem prazo de validade para execução. Na configuração padrão, esse prazo é de 45 minutos.

A expiração impede que uma proposta vencida seja utilizada normalmente, mas não significa que seu registro seja automaticamente apagado do armazenamento local.

### 5.3. Logs técnicos

Os registros são organizados em arquivos diários. A implementação analisada não possui uma rotina automática de exclusão desses arquivos por idade.

### 5.4. Demais arquivos locais

A Miku também pode armazenar informações operacionais, como a seleção de provedor e modelo de IA e a associação entre um servidor e um cargo privado criado pela aplicação.

Os arquivos de execução não fazem parte dos documentos públicos do repositório e são excluídos do controle de versão pelas regras do projeto.

## 6. Segurança

A implementação utiliza medidas técnicas para reduzir riscos, incluindo:

- Armazenamento local em arquivos JSON.
- Gravação atômica para reduzir riscos de corrupção de arquivos.
- Permissões restritivas de arquivo quando suportadas pelo sistema operacional.
- Separação das credenciais de IA em configuração local.
- Redação de determinados formatos de tokens e chaves nos logs.
- Verificações de permissão antes de operações administrativas.

Essas medidas não representam garantia absoluta de segurança. Os arquivos locais não possuem criptografia própria em repouso na implementação analisada. A proteção do computador ou servidor, dos backups, do sistema operacional e das credenciais também depende do operador responsável pela instalação.

## 7. Direitos e solicitações dos usuários

Os usuários podem solicitar informações sobre o tratamento de seus dados, bem como pedidos de acesso, correção ou exclusão, conforme os direitos aplicáveis previstos na legislação.

Para solicitações que envolvam dados armazenados localmente, incluindo registros técnicos e propostas administrativas, entre em contato pelo endereço indicado nesta política.

O comando `/limpar` remove o histórico de IA do usuário no contexto em que foi executado. Ele não apaga automaticamente logs, propostas administrativas ou outros registros operacionais.

A exclusão de uma mensagem diretamente no Discord também não significa que uma cópia já armazenada no histórico local da Miku será automaticamente removida.

## 8. Transferência internacional de dados

A utilização de provedores externos de inteligência artificial pode envolver o processamento de informações em servidores localizados fora do Brasil.

A localização e as condições desse processamento dependem do provedor e do endpoint configurado pelo operador da Miku.

Quando aplicável, o tratamento e a transferência internacional deverão observar os requisitos legais pertinentes.

## 9. Responsabilidades do operador

A pessoa ou entidade responsável por hospedar e operar a Miku deve proteger os arquivos locais, manter as credenciais em segurança, configurar adequadamente os provedores de IA e atender às solicitações legítimas dos titulares de dados.

A utilização da Miku também deve respeitar os Termos de Serviço do Discord, sua Política de Desenvolvedor e as demais regras aplicáveis à plataforma.

## 10. Alterações desta política

Esta Política de Privacidade poderá ser atualizada para refletir alterações nas funcionalidades, nos provedores de inteligência artificial, nas práticas de armazenamento ou nas exigências legais.

A versão vigente será publicada neste repositório.

## 11. Contato

Para dúvidas, solicitações relacionadas à privacidade ou pedidos referentes aos dados tratados pela Miku Bot:

**E-mail:** gustavodiastrabalhos@gmail.com

**Identificação Secundária:** Gustavo ou {Dash}
