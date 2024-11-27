# Registro de Atividades

Este documento contém as atividades realizadas nas aulas de Engenharia de Software. 

---

## 09/08 - Atividade: Trecho do livro _Software Engineering at Google_

> _"We see three critical differences between programming and software engineering: time, scale, and the trade-offs at play. On a software engineering project, engineers need to be more concerned with the passage of time and the eventual need for change. In a software engineering organization, we need to be more concerned about scale and efficiency, both for the software we produce as well as for the organization that is producing it. Finally, as software engineers, we are asked to make more complex decisions with higher-stakes outcomes, often based on imprecise estimates of time and growth."_  

**Resposta**:  
Esse trecho do livro aborda a diferença entre programação, que foca na resolução de problemas imediatos por meio de código, e a engenharia de software, que exige um pensamento sistêmico e de longo prazo, com planejamento para mudanças e impactos organizacionais.

---

## 12/08 - Atividade: Trade-offs

### 1. **Desempenho x Consumo de Energia**
- **Cenário**:  
  Um aplicativo móvel processa dados localmente para oferecer respostas rápidas.  
- **Trade-off**:  
  - **Vantagem**: Melhor desempenho e respostas imediatas ao usuário.  
  - **Desvantagem**: O consumo de bateria do dispositivo aumenta, impactando a usabilidade a longo prazo.

### 2. **Segurança x Tempo de Desenvolvimento**
- **Cenário**:  
  Uma equipe decide implementar criptografia avançada para proteger dados em um sistema simples de armazenamento.  
- **Trade-off**:  
  - **Vantagem**: O sistema será mais seguro contra acessos não autorizados.  
  - **Desvantagem**: A implementação leva mais tempo, atrasando a entrega do projeto.

### 3. **Confiabilidade x Custos**
- **Cenário**:  
  Um servidor secundário é configurado para manter o sistema online caso o principal falhe (alta disponibilidade).  
- **Trade-off**:  
  - **Vantagem**: O sistema torna-se mais confiável, minimizando o tempo de inatividade.  
  - **Desvantagem**: O custo de manter servidores adicionais é maior, impactando o orçamento.

---

## 01/11 - 4) Atividade diagrama de classes UML

[![Diagrama](https://github.com/clarol/bertoti/blob/64d8d05bb3cc1dc54e53491eb660a37b2eb40b4c/EngSoftware/uml_bertoti.png)]

---

## 22/11 - 5) Aprsentação do BOT com Ollama

https://github.com/thiagosabreu/TelegramChatBotWithOllama

# Registro de Atividades

Este documento contém registros de atividades realizadas no estudo de Java.

---

## 19/08 - Atividade: Java

### Classe `Planta`
```java
public class Planta {
    
    // Definindo as características básicas da planta: nome e tipo
    private String nome;  
    private String tipo;
    
    // Construtor para inicializar o nome e o tipo da planta 
    // Usamos 'this' para deixar claro que estamos referenciando os atributos da classe.
    public Planta(String nome, String tipo) {  
        this.nome = nome;
        this.tipo = tipo;
    }
    
    // Método para obter o nome da planta.
    public String getNome() {
        return nome;
    }
    
    // Método para alterar o nome da planta.
    public void setNome(String nome) {
        this.nome = nome;
    }
    
    // Método para obter o tipo da planta.
    public String getTipo() {
        return tipo;
    }
    
    // Método para alterar o tipo da planta.
    public void setTipo(String tipo) {
        this.tipo = tipo;
    }
}

import java.util.List;  
import java.util.LinkedList;

public class Floricultura {

    // Criando uma lista para armazenar todas as plantas cadastradas na Floricultura.
    private List<Planta> plantas = new LinkedList<>();

    // Método para cadastrar uma nova planta na Floricultura.
    public void cadastrarPlanta(Planta planta) {
        plantas.add(planta); // Adiciona a planta à lista de plantas.
    }
    
    // Método para buscar plantas pelo nome.
    // Se tiver mais de uma planta com o mesmo nome, todas serão retornadas.
    public List<Planta> buscarPlantaPorNome(String nome) {
        List<Planta> plantasEncontradas = new LinkedList<>(); // Lista para guardar as plantas encontradas.
        for (Planta planta : plantas) {  // Percorre a lista de plantas cadastradas.
            if (planta.getNome().equals(nome)) { // Verifica se o nome da planta corresponde ao nome buscado.
                plantasEncontradas.add(planta); // Adiciona a planta encontrada à lista.
            }
        }
        return plantasEncontradas; // Retorna a lista de plantas encontradas.
    }
    
    // Método para obter a lista completa de todas as plantas cadastradas na Floricultura.
    public List<Planta> getPlantas() {
        return plantas;
    }
}

import static org.junit.jupiter.api.Assertions.*;  
import java.util.List;

import org.junit.jupiter.api.Test;

class TesteFloricultura {

    @Test
    void test() {
        
        // Crio uma nova floricultura, onde vou cadastrar as plantas para os testes.
        Floricultura floricultura = new Floricultura(); 
        
        // Crio e nomeio duas novas plantas: uma orquídea chamada Azul e uma rosa chamada Sol.
        Planta azul = new Planta("Azul", "Orquidea"); 
        Planta sol = new Planta("Sol", "Rosa");
        
        // Cadastro as plantas na floricultura.
        floricultura.cadastrarPlanta(azul);
        floricultura.cadastrarPlanta(sol);
        
        // Verifico se o número de plantas cadastradas na floricultura é 2.
        assertEquals(floricultura.getPlantas().size(), 2);
        
        // Busco a planta chamada Sol e verifico se o tipo dela é o mesmo que foi definido inicialmente (rosa).
        List<Planta> solPlantas = floricultura.buscarPlantaPorNome("Sol");
        assertEquals(solPlantas.get(0).getTipo(), sol.getTipo());
    }
}

---




