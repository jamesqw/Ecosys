#Ecosys 
É um sistema de gerenciamento de ambiente multiplataforma baseado na Peregrine Labs, desenvolvido originalmente para pesquisa e desenvolvimento de produção VFX/Animação, mas pode ser usado em qualquer situação em que uma compreensão precisa do seu ambiente de trabalho seja importante (e realmente deve ser!).

Por quê?
Embora possa parecer uma tarefa simples, ainda é muito comum encontrar muitos estúdios com os quais trabalhamos que não têm controle sobre seu ambiente, o que é a raiz de muitos problemas (versões erradas de software sendo acessadas, versões erradas de objetos compartilhados, versões incompatíveis, etc.). A nossa esperança é que o Ecosystem possa ser usado não apenas para resolver esses problemas, mas também para melhorar o fluxo de trabalho em geral.

O conjunto de ferramentas funciona extremamente bem em nossa casa, mas as suposições que fizemos podem não se encaixar em todos os fluxos de trabalho ou pipelines - nossa esperança é que os estúdios interessados em usar o Ecosystem forneçam feedback para torná-lo mais flexível e, portanto, mais geral em escopo.

Para mais informações sobre os conceitos de design, consulte nossa apresentação da conferência TDForum 2012 - Building and Leveraging a Cross Platform VFX/Animation Development Environment

Detalhes
Existem muitas situações em que pode ser necessário trabalhar em várias versões do mesmo software e/ou compartilhar dados entre aplicativos que provavelmente são muito pedantes em relação à compatibilidade, na maioria das vezes tudo isso pode ser controlado por meio de variáveis de ambiente em um shell. Definir manualmente as variáveis de ambiente e/ou garantir que as dependências sejam resolvidas corretamente geralmente está fora de questão, é aí que entra o Ecosystem.

Cada instância de uma ferramenta tem um arquivo .env que define o nome base do produto, a versão e como o ambiente deve ser, parâmetros "opcionais" podem ser incluídos para alterar a maneira como o ambiente é resolvido se outras ferramentas estiverem presentes.

Com esta biblioteca de ferramentas e versões, o script ecosystem.py é então usado em um ambiente limpo (ou seja, apenas o mínimo necessário de variáveis definidas) para resolver dependências e definir o ambiente em um estado onde as ferramentas solicitadas possam ser usadas juntas.

Por exemplo:

Copy code
eneed maya2014,vray3.05,yeti1.3.10
me dará um ambiente de trabalho onde o maya executará o Maya 2014 e o Yeti 1.3.10 e o Vray 3.05 serão configurados corretamente.

O Ecosys foi desenvolvido para ser multiplataforma, portanto, o exemplo acima funciona no Linux, Osx e Windows.

Embora a intenção seja que o Ecosystem seja usado a partir de um shell, a fonte .py é escrita de forma que seria fácil incorporá-la em um aplicativo GUI para ter um iniciador mais visual.

Começando
Recentemente, atualizamos como o Ecosystem pode ser usado tanto na linha de comando quanto como um módulo
