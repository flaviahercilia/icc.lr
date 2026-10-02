# Achados e Perdidos UFRPE: Documento de Requisitos
> Atividade prática de Levantamento de Requisitos (ICC / UFRPE).
> Atividade de prática: não é entregue e não vale nota.

## 1. Equipe
| Nome | Curso |
|------|-------|
| Flavia Hercilia da Silva | Ciência da Computação |

## 2. Visão geral
**Problema:** objetos perdidos no campus da [UFRPE](https://www.ufrpe.br) ficam espalhados entre
portarias, secretarias e grupos de mensagem, e raramente voltam ao dono.

**Solução proposta:** propõe-se o desenvolvimento de um sistema web de achados e perdidos com o objetivo de centralizar o cadastro de itens encontrados, a consulta de objetos perdidos e o processo de devolução aos respectivos proprietários.

**Escopo:** O sistema inclui funcionalidades para cadastro de itens achados, busca de itens perdidos por categoria e data, autenticação de usuários, comprovação de posse e confirmação de entrega por administrador. Ficam fora do escopo a entrega física dos objetos, a mediação de conflitos relacionados à posse e qualquer responsabilidade legal sobre os itens cadastrados.

## 3. Atores (usuários do sistema)
| Ator | Descrição | O que precisa fazer |
|------|-----------|---------------------|
| Usuário | Aluno com matrícula ativa | Procurar objetos perdidos, registrar perdas |
| Ponto de guarda | Portaria, biblioteca ou secretaria responsável por guardar o objeto | Cadastrar itens encontrados, manter o item seguro até a retirada. |
| Administrador | Responsável pela gestão do sistema | Analisar solicitações, validar comprovação de posse, confirmar a entrega dos itens aos proprietários. |

## 4. Requisitos funcionais
> Formato: código, nome, descrição, ator, prioridade e critérios de aceitação.

### RF01: Cadastrar item achado
- **Descrição:** o sistema deve permitir que um usuário registre um item encontrado, informando foto, descrição, categoria, local onde foi achado e data do achado.
- **Ator:** Usuário, Ponto de guarda
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] Os campos categoria, local e data são obrigatórios.
- [ ] A foto do item é opcional.
- [ ] O item aparece na busca logo após ser salvo.
- [ ] O sistema registra o item na lista de objetos encontrados.

### RF02: Buscar itens perdidos
- **Descrição:** o sistema deve permitir que um usuário busque itens perdidos por palavra-chave e filtre os resultados por categoria e data.
- **Ator:** Usuário, Ponto de guarda
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] O usuário pode pesquisar por palavra-chave.
- [ ] O usuário pode filtrar os resultados por categoria/data
- [ ] A busca apresenta os itens encontrados de forma organizada.

### RF03: Comprovar posse
- **Descrição:** o sistema deve solicitar uma comprovação de posse antes de permitir a retirada do item, exigindo informações ou documentos que ajudem a confirmar que o solicitante é o verdadeiro proprietário.
- **Ator:** Usuário
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] O sistema solicita comprovação de posse antes da liberação do item.
- [ ] O usuário deve informar dados específicos do objeto que não sejam evidentes apenas pela foto pública.
- [ ] O usuário pode anexar documentos ou informações complementares.
- [ ] A solicitação de retirada só é aceita após o envio da comprovação.

### RF04: Confirmar entrega
- **Descrição:** o sistema deve permitir que um administrador confirme a entrega de um item ao seu respectivo proprietário, registrando a finalização do processo.
- **Ator:** Administrador
- **Prioridade:** Alta
- **Critérios de aceitação:**
- [ ] Apenas usuários com perfil de administrador podem confirmar entregas.
- [ ] O sistema registra a data e hora da entrega.
- [ ] O administrador pode visualizar o histórico da entrega.

## 5. Requisitos não funcionais
| Código | Categoria | Requisito | Como medir |
|--------|-----------|-----------|------------|
| RNF01 | Usabilidade | Funcionar em celular e computador | Testar em telas diferentes |
| RNF02 | Desempenho | Busca responde rápido | Resultado em até 2 segundos |
| RNF03 | Segurança | Autenticação de usuários para acesso às funcionalidades restritas | Login obrigatório para ações administrativas e de retirada |

## 6. Regras de negócio
- **RN01:** Documentos como RG, CNH e cartão não exibem foto pública.
- **RN02:** A retirada do item depende de comprovação de posse.
- **RN03:** Somente usuários autenticados podem cadastrar, solicitar retirada e confirmar entrega.
- **RN04:** Somente administradores podem validar a posse e concluir a entrega.

## 7. Histórias de usuário
- Como **usuário**, quero **buscar meu item perdido pela categoria, data e local**, para **saber se alguém o encontrou**.
- Como **usuário**, quero **solicitar a devolução de um item encontrado**, para **recuperar meus pertences**.
- Como **usuário**, quero **registrar a perda de um item**, para **aumentar as chances do item ser recuperado**.
- Como **ponto de guarda**, quero **visualizar as solicitações de retirada**, para **encaminhar os itens corretamente aos responsáveis**.
- Como **administrador**, quero **validar a comprovação de posse**, para **garantir que o item seja entregue ao verdadeiro proprietário**.

## 8. Dúvidas em aberto
- [ ] Os objetos ficam guardados em um só lugar ou em vários pontos?
- [ ] Validação de Posse: Se duas pessoas reivindicarem o mesmo objeto e enviarem comprovações, qual será o protocolo do Administrador?
- [ ] Destino de Itens Esquecidos: Qual será o tempo máximo de retenção de um objeto no ponto de guarda antes que ele seja doado ou descartado?
