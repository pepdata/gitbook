# Propagação do Risco

A informação que adiciona nos questionários é partilhada entre diferentes páginas. Exemplificando, caso adicione a mesma pessoa como cliente e fornecedor, a ação de alterar a sua informação enquanto cliente poderá alterar também o seu risco enquanto fornecedor.&#x20;

## Submissão de questionário e recálculo do risco

A propagação do risco ocorrerá no momento da submissão do questionário. Os riscos dos questionários em outras páginas que compartilham as mesmas informações serão recalculados e o risco do questionário atual será propagado para os questionários relacionados.

### 1 - Recálculo do risco dos questionários que partilham a mesma informação

O sistema recalcula automaticamente a categoria de risco dos questionários nas outras páginas que partilham a mesma informação. Este recálculo é necessário para refletir qualquer alteração nos dados que possa influenciar a avaliação do risco. Se o recálculo resultar numa alteração da categoria de risco, o sistema lançará um alerta.

### 2 - Recálculo do risco dos questionários relacionados

Após a submissão de um questionário, é iniciado um processo de recálculo de todos os questionários relacionados. A propagação é extensível a todos os questionários ascendentes que não sejam também descendentes, isto ocorre para que não exista a propagação de risco dentro de relações cíclicas. **Exemplo 1:**

* Empresa A
  * Representante A

Caso seja submetido o questionário da "Empresa A", não será recalculado o risco do questionário do "Representante A".\
Por sua vez, caso seja submetido o questionário do "Representante A", o seu risco será propagado para o questionário da "Empresa A", o que levará ao recálculo do seu risco. Se o recálculo resultar numa alteração da categoria de risco, o sistema lançará um alerta.

**Exemplo 2 (relação cíclica):**&#x20;

* Empresa A
  * Empresa B
* Empresa B
  * Empresa A

Quando acontece a submissão do questionário da "Empresa B", o seu risco não é propagado para o questionário da "Empresa A", nem terá influência no recálculo do risco deste último, uma vez que ambos fazem parte de uma relação cíclica.  Se o recálculo resultar numa alteração da categoria de risco, o sistema lançará um alerta.



