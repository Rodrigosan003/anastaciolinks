# Ideias para deixar o projeto mais dinâmico com JavaScript

O projeto já apresenta os links de forma simples e responsiva. Como a página tem poucos elementos e não precisa de servidor, o JavaScript pode acrescentar interações leves sem complicar a manutenção. O arquivo `assets/JS/script.js` está disponível para implementar essas melhorias.

## Ideias recomendadas

### 1. Animação de entrada dos elementos

Fazer o perfil e os cartões de link aparecerem suavemente quando a página carregar, com um pequeno intervalo entre cada cartão. Isso dá uma sensação de movimento sem exigir interação.

- Use uma classe CSS para controlar a animação e o JavaScript apenas para ativá-la.
- Respeite a preferência de movimento reduzido do sistema (`prefers-reduced-motion`).
- **Dificuldade:** fácil.

### 2. Botão para compartilhar a página

Adicionar um botão “Compartilhar perfil” que use a Web Share API em celulares e navegadores compatíveis. Se o recurso não estiver disponível, copiar a URL da página para a área de transferência e mostrar uma confirmação.

- Use `navigator.share` quando disponível e `navigator.clipboard.writeText` como alternativa.
- Exiba uma mensagem acessível como “Link copiado!” e faça-a desaparecer após alguns segundos.
- **Dificuldade:** fácil.

### 3. Botão para copiar o contato

Se quiser facilitar o contato direto, adicionar um botão para copiar o e-mail ou outro dado de contato, caso ele seja incluído na página. A confirmação visual ajuda a pessoa a saber que a ação funcionou.

- Evite exibir ou copiar dados pessoais que não queira tornar públicos.
- Trate possíveis falhas ao acessar a área de transferência.
- **Dificuldade:** fácil.

### 4. Alternância entre tema claro e escuro

Criar um controle para alternar as cores da página entre dois temas. O JavaScript pode trocar um atributo ou uma classe no elemento `<html>`, enquanto as cores ficam organizadas em variáveis CSS.

- Manter a escolha com `localStorage`, para que o tema continue após recarregar a página.
- Considerar o tema do sistema como escolha inicial (`prefers-color-scheme`).
- Garantir que o botão tenha nome acessível e indique o tema atual.
- **Dificuldade:** média.

### 5. Efeito de interação nos links

Ao focar ou clicar em um link, aplicar um destaque breve no cartão correspondente. Isso pode reforçar a resposta da interface, especialmente em telas sensíveis ao toque.

- Preserve o indicador de foco para quem navega com teclado.
- Evite efeitos que atrasem a abertura dos links.
- **Dificuldade:** fácil.

### 6. Atualização automática do ano no rodapé

Substituir o ano fixo do copyright pelo ano atual calculado com `new Date().getFullYear()`. Assim, o texto não precisa ser atualizado manualmente todo ano.

- Marque no HTML apenas o trecho do ano com um identificador ou atributo `data-*`.
- **Dificuldade:** muito fácil.

### 7. Saudação conforme o horário

Mostrar uma saudação curta, como “Bom dia”, “Boa tarde” ou “Boa noite”, com base na hora local do visitante.

- Mantenha o nome e as informações principais visíveis mesmo se o JavaScript estiver desativado.
- Use a hora local do navegador; não é necessário consultar um serviço externo.
- **Dificuldade:** fácil.

## Uma boa ordem para implementar

1. Atualização automática do ano.
2. Animação de entrada, com suporte a movimento reduzido.
3. Compartilhamento ou cópia do endereço da página.
4. Alternância de tema, se combinar com a identidade visual desejada.

## Boas práticas

- Prefira JavaScript puro: as interações sugeridas não exigem bibliotecas.
- Mantenha o conteúdo dos links no HTML, para que a página continue útil sem JavaScript.
- Use o JavaScript para melhorar a experiência, sem impedir a navegação normal.
- Teste no celular, no computador e com teclado.
- Evite adicionar busca ou filtros por enquanto: com poucos links, eles podem deixar a interface mais complexa sem trazer muito benefício.
