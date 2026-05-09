## 💰 2. Gestão de Caixa e Automação de Troco
[cite_start]**Contexto:** Frente de Loja / Vendas[cite: 20, 22].

[cite_start]Este algoritmo visa garantir a precisão no cálculo do troco e a eficiência logística na entrega das cédulas ao cliente[cite: 44].

### Arquitetura da Solução
* [cite_start]**Validação de Pagamento:** Verifica se o valor pago é suficiente para cobrir o total da compra[cite: 37, 76, 77].
* [cite_start]**Cálculo de Troco:** Determina a diferença exata a ser devolvida[cite: 38, 41, 82].
* [cite_start]**Decomposição em Notas:** Transforma o valor do troco na menor quantidade possível de notas (100, 50, 10, 5, 1) utilizando operações de divisão inteira (`DIV`) e resto (`MOD`)[cite: 16, 44, 46].

### Exemplo de Lógica Aplicada
```pascal
// Cálculo para a maior cédula disponível
nota100 := resto DIV 100;
resto := resto MOD 100;

// Exibição condicional (apenas se houver nota)
Se nota100 > 0 Então
    Escreva (nota100, " nota(s) de 100");
FimSe
🧠 Reflexão Crítica (Pensamento Computacional)O desenvolvimento destes projetos permitiu uma mudança de perspetiva sobre a resolução de problemas:  A Nova Lente: Programar funciona como um "par de óculos novos", permitindo enxergar a lógica por trás do caos cotidiano.Precisão e Plano B: A necessidade de dar ordens exatas ao computador ensina a prever erros e a preparar planos de contingência antes mesmo de os obstáculos surgirem.Decomposição: Problemas grandes e complexos (como a gestão de um hospital ou de um caixa) são divididos em pedaços menores e mais práticos de resolver.🚀 Como UtilizarConsulte os Fluxogramas para uma compreensão visual dos processos.  Analise os ficheiros de Pseudocódigo para entender as regras de negócio e validações.  Os códigos estão prontos para tradução para linguagens de alto nível como Python ou C.
