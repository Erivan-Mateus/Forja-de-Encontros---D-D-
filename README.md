# Forja de Encontros
Ferramenta local, não oficial, para D&D. Abra index.html em um navegador moderno após extrair o ZIP. Não precisa instalar dependências nem usar internet. Para hospedagem estática, publique a pasta inteira. Alternativamente, rode `python -m http.server 8000` dentro dela e abra http://localhost:8000.

## Uso
1. Configure nível (1–20), jogadores, dificuldade, ambiente, tipo e composição.
2. Gere um encontro de 1–10 criaturas. Repetições são agrupadas.
3. Salve, exporte ou inicie na Arena. Cada inimigo tem PV e iniciativa independentes.
4. Importe fichas JSON na aba Importar. O modelo pode ser baixado na própria página.

## Dados
O catálogo inicial tem 32 criaturas de demonstração, com fichas parciais e valores não conferidos individualmente com o Livro dos Monstros 2025. Não é uma reprodução do livro. Substitua ou amplie com dados autorizados e conferidos. `data/monsters.json` é uma cópia importável dos dados iniciais; `data/monsters.js` permite abrir o site diretamente sem servidor. Alterar somente o JSON não altera o catálogo inicial: importe-o na interface. O importador aceita uma lista ou `{ "monstros": [...] }`, valida campos básicos e substitui registros com IDs iguais. Campos extras são mantidos. Use ND numérico (0.125 para 1/8), XP inteiro, e PV/CA numéricos em `ficha`. Grupos são etiquetas compartilhadas para encontros temáticos. Ambientes e grupos são normalizados sem acentos. Fichas completas são exibidas como dados estruturados, sem automação de ataques.

## Dificuldade
Orçamentos por personagem de baixo, moderado e alto seguem a tabela de referência do DMG 2024; Brincadeira = metade do baixo e Morte quase certa = 1,75 vezes o alto. As faixas são separadas pelos pontos médios dos alvos. O algoritmo amostra combinações e retorna a mais próxima encontrada, indicando quando não corresponde à dificuldade pedida. Não é busca exaustiva nem simulação de combate. Ações lendárias, sinergias e economia de ações não são modeladas. Horda exige 5–10 criaturas, Chefe exige 1, Chefe e lacaios exige 2–10 e uma etiqueta de grupo compartilhada.

## Persistência
Dados são armazenados no localStorage do navegador, por origem. Exporte bestiário e combates como backup. Limpar os dados do navegador pode apagar os registros. Navegadores podem restringir armazenamento em arquivos locais; nesse caso use o servidor local acima. A arena persiste no mesmo navegador; não há contas ou sincronização em nuvem.
