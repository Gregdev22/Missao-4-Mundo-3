<!-- PROJECT LOGO -->
<div align="center">
   <a href="https://github.com/othneildrew/Best-README-Template">
      <img src="https://logodownload.org/wp-content/uploads/2014/12/estacio-logo-1-2048x1641.png" alt="estacio logo" width="80"                  height="80">
   </a>
    <h1 align="center"> Universidade Estácio de Sá </h1>
     <hr>
</div> 

* DESENVOLVIMENTO FULL STACK- TURMA 23.3 -9003
* Disciplina: RPG0017  - Vamos Integrar Sistemas.
* Semestre Letivo: 2023.2
* Repositorio Git: https://github.com/Gregdev22/Missao-4-Mundo-3

<hr>

* [EMERSON GREGORIO ALVES](https://github.com/Gregdev22) - MATRICULA: 2022.0908.4986
<hr>
 <h1 align="center"> Missão Prática | Nível 4 | Mundo 3 </h1>
 <h2 align="left" > Implementação de sistema cadastral com interface Web, baseado nas tecnologias deServlets, JPA e JEE. </h2> 
 <h3>Procedimento 1: Camadas de Persistência e Controle </h3>
 <h3>Procedimento 2: Interface Cadastral com Servlet e JSPs </h3>
 <h3>Procedimento 3: Melhorando o Design da Interface </h3>
 <hr>

 <h2> :clipboard: Objetivos da Prática </h2>

* Implementar persistência com base em JPA.
* Implementar regras de negócio na plataforma JEE, através de EJBs.
* Implementar sistema cadastral Web com   base em Servlets e JSPs.
* Utilizar a biblioteca Bootstrap para melhoria do design.
* No final do exercício, o aluno terá criado todos os elementos necessários para exibição e entrada de dados na plataforma Java Web, tornando-se capacitado para
lidar com contextos reais de aplicação.
<hr>

<h2> Códigos </h2>

[Procedimento 1: Camadas de Persistência e Controle](https://github.com/Gregdev22/Missao-4-Mundo-3/tree/main/Procedimento%201)

* ServletProduto.java

``` java
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/JSP_Servlet/Servlet.java to edit this template
 */
package cadastroee.servlets;

import cadastroee.controller.ProdutoFacadeLocal;
import jakarta.ejb.EJB;
import java.io.IOException;
import java.io.PrintWriter;
import jakarta.servlet.ServletException;
import jakarta.servlet.annotation.WebServlet;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;
import cadastroee.model.Produto;


/**
 *
 * @author grego
 */

@WebServlet("/ServletProduto")
public class ServletProduto extends HttpServlet {
    
    @EJB
    ProdutoFacadeLocal facade;

    /**
     * Processes requests for both HTTP <code>GET</code> and <code>POST</code>
     * methods.
     *
     * @param request servlet request
     * @param response servlet response
     * @throws ServletException if a servlet-specific error occurs
     * @throws IOException if an I/O error occurs
     */
    
    protected void processRequest(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
            response.setContentType("text/html;charset=UTF-8");
        try (PrintWriter out = response.getWriter()) {
            /* TODO output your page here. You may use following sample code. */
            out.println("<!DOCTYPE html>");
            out.println("<html>");
            out.println("<head>");
            out.println("<title>Servlet ServletProduto</title>");            
            out.println("</head>");
            out.println("<body>");
           // out.println("<h1>Servlet ServletProduto at " + request.getContextPath() + "</h1>");
            //out.println(facade.findAll().getClass());
            //out.println(facade.find(1).getClass());
            
            for (Produto p : facade.findAll()) {
                out.println("<li>" + p.getNome() + "</li>");
            }
           
            out.println("</body>");
            out.println("</html>");
        }
    }

    // <editor-fold defaultstate="collapsed" desc="HttpServlet methods. Click on the + sign on the left to edit the code.">
    /**
     * Handles the HTTP <code>GET</code> method.
     *
     * @param request servlet request
     * @param response servlet response
     * @throws ServletException if a servlet-specific error occurs
     * @throws IOException if an I/O error occurs
     */
    @Override
    protected void doGet(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        processRequest(request, response);
    }

    /**
     * Handles the HTTP <code>POST</code> method.
     *
     * @param request servlet request
     * @param response servlet response
     * @throws ServletException if a servlet-specific error occurs
     * @throws IOException if an I/O error occurs
     */
    @Override
    protected void doPost(HttpServletRequest request, HttpServletResponse response)
            throws ServletException, IOException {
        processRequest(request, response);
    }

    /**
     * Returns a short description of the servlet.
     *
     * @return a String containing servlet description
     */
    @Override
    public String getServletInfo() {
        return "Short description";
    }// </editor-fold>

}

```
<br>

[Procedimento 2: Interface Cadastral com Servlet e JSPs](https://github.com/Gregdev22/Missao-4-Mundo-3/tree/main/Procedimento%202)

* ServletProdutoFC.java
```java
```

* ProdutoLista.jsp
```jsp
```

* ProdutoDados.jsp
```jsp
```
