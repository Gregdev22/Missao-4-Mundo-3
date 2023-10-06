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

* ServletProduto.java
```java
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

* ServletProdutoFC.java
```java
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/JSP_Servlet/Servlet.java to edit this template
 */
package cadastroee.servlets;

import cadastroee.controller.ProdutoFacadeLocal;
import cadastroee.model.Produto;
import jakarta.ejb.EJB;
import jakarta.servlet.RequestDispatcher;
import jakarta.servlet.annotation.WebServlet;
import java.io.IOException;
import java.io.PrintWriter;
import jakarta.servlet.ServletException;
import jakarta.servlet.http.HttpServlet;
import jakarta.servlet.http.HttpServletRequest;
import jakarta.servlet.http.HttpServletResponse;

/**
 *
 * @author grego
 */

@WebServlet(name="ServletProdutoFC", urlPatterns = {"/ServletProdutoFC"})
public class ServletProdutoFC extends HttpServlet {

    @EJB
    ProdutoFacadeLocal facade;
    
    int idAtual =6;
    
    public int aleatorio() {
        // Math.random() gera um número aleatório entre 0.0 e 0.999
        // Assim, Math.random()*5 estará entre 0.0 e 4.999
        double doubleRandomNumber = Math.random() * 100;
        int randomNumber = (int)doubleRandomNumber;
        return randomNumber;
    }
   

     
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
              String acao = request.getParameter("acao"); 
              String destino = "";
              
              if(acao != null){
              switch(acao){
                                   
                   case "listar":
                    request.setAttribute("lista", facade.findAll());
                    destino = "ProdutoLista.jsp";
                    break;
                    
                   case "excluir":
                    int idProduto = Integer.valueOf(request.getParameter("idproduto")); 
                    facade.remove(facade.find(idProduto));
                    request.setAttribute("lista", facade.findAll());
                    RequestDispatcher rd = request.getRequestDispatcher("ProdutoLista.jsp");
                    rd.forward(request, response);
                    break;
                 
                  case "formIncluir":
                    destino = "ProdutoDados.jsp";
                    break;
                  
                  case "formAlterar":
                    int id_produto = Integer.valueOf(request.getParameter("idproduto"));
                    request.setAttribute("lista", facade.find(id_produto));
                    destino = "ProdutoDados.jsp";
                    break;
        }
                    RequestDispatcher rd = request.getRequestDispatcher(destino);
                    rd.forward(request, response);
                    
            } else{
                    request.setAttribute("lista", facade.findAll());
                    RequestDispatcher rd = request.getRequestDispatcher("ProdutoLista.jsp");
                    rd.forward(request, response);
    }}
    
    
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
                    
                    String acao = request.getParameter("acao"); 
                    
                    switch(acao){
                        
                        case("alterar"):
                            int produtoID = Integer.valueOf(request.getParameter("idproduto")); 
                            String nome = request.getParameter("nome");
                            int quantidadeProduto = Integer.valueOf(request.getParameter("quantidade"));
                            float precoProduto = Float.valueOf(request.getParameter("preco"));
                            Produto produtoAlterar = facade.find(produtoID);
                            produtoAlterar.setNome(request.getParameter("nome"));
                            produtoAlterar.setQuantidade(quantidadeProduto);
                            produtoAlterar.setPrecoVenda(precoProduto);
                            facade.edit(produtoAlterar);
                            request.setAttribute("lista", facade.findAll());
                            RequestDispatcher rd = request.getRequestDispatcher("ProdutoLista.jsp");
                            rd.forward(request, response);
                            break;
                        
                        case("incluir"):
                            int idNext = aleatorio(); 
                            
                            if (idNext != idAtual){
                                float preco = Float.valueOf(request.getParameter("preco"));
                                String nome2 = request.getParameter("nome");
                                int quantidade = Integer.valueOf(request.getParameter("quantidade"));
                                Produto produto = new Produto(idNext,
                                        request.getParameter("nome"), 
                                        quantidade, 
                                        preco);
                                facade.create(produto);
                                request.setAttribute("lista", facade.findAll());
                                idAtual = idNext;
                                RequestDispatcher rd2 = request.getRequestDispatcher("ProdutoLista.jsp");
                                rd2.forward(request, response);
                                break;
                            } else {
                                idNext = idNext++;
                                idAtual = idNext;
                                float preco = Float.valueOf(request.getParameter("preco"));
                                String nome2 = request.getParameter("nome");
                                int quantidade = Integer.valueOf(request.getParameter("quantidade"));
                                Produto produto = new Produto(idNext,
                                        request.getParameter("nome"), 
                                        quantidade, 
                                        preco);
                                facade.create(produto);
                                request.setAttribute("lista", facade.findAll());
                                idAtual = idNext;
                                RequestDispatcher rd2 = request.getRequestDispatcher("ProdutoLista.jsp");
                                rd2.forward(request, response);
                                break;
                            }        
                    }          
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

* ProdutoLista.jsp
```jsp
<%-- 
    Document   : ProdutoLista
    Created on : 3 de out. de 2023, 21:16:09
    Author     : grego
--%>


<%@page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>


<%@page import="cadastroee.model.Produto"%>
<%@page import="java.util.ArrayList"%>
<%@page import="java.util.List"%>
<%@page import="cadastroee.controller.ProdutoFacadeLocal"%>



<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title>JSP Page</title>
    </head>
    <body>
        <div>
            <h1>Listagem de Produtos</h1>
            <h3>
                <a href="ServletProdutoFC?acao=formIncluir"> Novo Produto  </a>
                <!-- <a href="ServletProdutoFC">  Atualizar Dados  </a> !-->
            </h3>
            
            <table border="1" width="100%">
                <tr>
                    <td> ID </td>
                    <td> Nome </td>
                    <td> Quantidade </td>
                    <td> Preco de Venda </td>
                    <td> Opções </td>
                </tr>
                
                <% 
                    try{
                    List<Produto> lista = (List) request.getAttribute("lista");
                        for(Produto p: lista){
                %>
                <tr>
                    <td>
                        <%=p.getIdproduto()%>
                    </td>
                    <td>
                        <%=p.getNome()%>
                    </td>
                    <td>
                        <%=p.getQuantidade()%>
                    </td>
                    <td>
                        <%=p.getPrecoVenda()%>
                    </td>
                    <td>
                        <a href="ServletProdutoFC?acao=formAlterar&idproduto=<%=p.getIdproduto()%>"> Alterar </a>
                        <a href="ServletProdutoFC?acao=excluir&idproduto=<%=p.getIdproduto()%>"> Excluir </a>
                    </td>
                    
                </tr>
                <% }
                        } catch(NullPointerException nexc){
                        out.print("<h1>"+nexc.getMessage()+"</h1>");
                        
                  }    

                %> 

                
            </table>
        </div>
    </body>
</html>
```

* ProdutoDados.jsp
```jsp
<%-- 
    Document   : ProdutoDados
    Created on : 5 de out. de 2023, 14:26:07
    Author     : grego
--%>

<%@page contentType="text/html" pageEncoding="UTF-8"%>

<%@page import="cadastroee.model.Produto"%>
<%@page import="java.util.ArrayList"%>
<%@page import="java.util.List"%>
<%@page import="cadastroee.controller.ProdutoFacadeLocal"%>

<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <title>JSP Page</title>
    </head>
    <body>
        
         <% 
            try{
                Produto produto = (Produto) request.getAttribute("lista");
                if (produto != null){
        %>
        
                <h1> Dados do Produto </h1>
                <form action="ServletProdutoFC" method="post" >
                    <input type="hidden" name="acao" value="alterar">
                    <input type="hidden" name="idproduto" value="<%=produto.getIdproduto()%>">
                    Nome: <input name="nome" value="<%=produto.getNome()%>"/>
                    Quantidade: <input name="quantidade" value="<%=produto.getQuantidade()%>"/>
                    Preco de Venda: <input name="preco" value="<%=produto.getPrecoVenda()%>"/>
                    <input type="submit" value="Alterar Produto"/>

                </form>
         <% 
             } else {
         %>    
                <h1> Dados do Produto </h1>
                <form action="ServletProdutoFC" method="post" >
                <input type="hidden" name="acao" value="incluir">
                Nome: <input name="nome"/>
                Quantidade: <input name="quantidade"/>
                Preco de Venda: <input name="preco"/>
                <input type="submit" value="Adicionar Produto"/>
                </form>
        <%                    
                    }  
                    } catch(ClassCastException nexc){
                     out.print("<h1>"+nexc.getMessage()+"</h1>");}
        %>
    </body>
</html>
```
<br>

[Procedimento 3: Melhorando o Design da Interface](https://github.com/Gregdev22/Missao-4-Mundo-3/tree/main/Procedimento%203)

* ProdutoLista.jsp
```jsp
<%-- 
    Document   : ProdutoLista
    Created on : 3 de out. de 2023, 21:16:09
    Author     : grego
--%>


<%@page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>


<%@page import="cadastroee.model.Produto"%>
<%@page import="java.util.ArrayList"%>
<%@page import="java.util.List"%>
<%@page import="cadastroee.controller.ProdutoFacadeLocal"%>



<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">        <title>JSP Page</title>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>        
    </head>
    
    <body class="container">
        <div>
            <h1>Listagem de Produtos</h1>
            <h3>
                <a class="btn btn-primary m-2" href="ServletProdutoFC?acao=formIncluir"> Novo Produto  </a>
                <!-- <a href="ServletProdutoFC">  Atualizar Dados  </a> !-->
            </h3>
            
            <table class="table table-striped"  border="1" width="100%">
                <tr class="table-dark">
                    <td> ID </td>
                    <td> Nome </td>
                    <td> Quantidade </td>
                    <td> Preco de Venda </td>
                    <td> Opções </td>
                </tr>
                
                <% 
                    try{
                    List<Produto> lista = (List) request.getAttribute("lista");
                        for(Produto p: lista){
                %>
                <tr>
                    <td>
                        <%=p.getIdproduto()%>
                    </td>
                    <td>
                        <%=p.getNome()%>
                    </td>
                    <td>
                        <%=p.getQuantidade()%>
                    </td>
                    <td>
                        <%=p.getPrecoVenda()%>
                    </td>
                    <td>
                        <a class="btn btn-primary btn-sm" href="ServletProdutoFC?acao=formAlterar&idproduto=<%=p.getIdproduto()%>"> Alterar </a>
                        <a class="btn btn-danger btn-sm" href="ServletProdutoFC?acao=excluir&idproduto=<%=p.getIdproduto()%>"> Excluir </a>
                    </td>
                    
                </tr>
                <% }
                        } catch(NullPointerException nexc){
                        out.print("<h1>"+nexc.getMessage()+"</h1>");
                        
                  }    

                %> 

                
            </table>
        </div>
    </body>
</html>
```

* ProdutoDados.jsp
```jsp
<%-- 
    Document   : ProdutoDados
    Created on : 5 de out. de 2023, 14:26:07
    Author     : grego
--%>

<%@page contentType="text/html" pageEncoding="UTF-8"%>

<%@page import="cadastroee.model.Produto"%>
<%@page import="java.util.ArrayList"%>
<%@page import="java.util.List"%>
<%@page import="cadastroee.controller.ProdutoFacadeLocal"%>

<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">        <title>JSP Page</title>
        <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
    </head>
    <body class="container">
        
         <% 
            try{
                Produto produto = (Produto) request.getAttribute("lista");
                if (produto != null){
        %>
        
                <h1> Dados do Produto </h1>
                <form class="form" action="ServletProdutoFC" method="post" >
                    <input type="hidden" name="acao" value="alterar">
                    <input type="hidden" name="idproduto" value="<%=produto.getIdproduto()%>">
                    <div class=" mb-3"> 
                        <label class="form-label"> Nome: </label>   
                        <input class="form-control" name="nome" value="<%=produto.getNome()%>"/>
                    </div>
                    <div class=" mb-3"> 
                        <label class="form-label">Quantidade: </label>  
                        <input class="form-control" name="quantidade" value="<%=produto.getQuantidade()%>"/>
                    </div>
                     <div class=" mb-3"> 
                         <label class="form-label"> Preco de Venda: </label>
                         <input class="form-control" name="preco" value="<%=produto.getPrecoVenda()%>"/>
                    </div>
                    <div class=" mb-3"> 
                        <input class=" btn btn-primary" type="submit" value="Alterar Produto"/>
                    </div>
                    

                </form>
         <% 
             } else {
         %>    
                <h1> Dados do Produto </h1>
                <form class="form" action="ServletProdutoFC" method="post" >
                    <input type="hidden" name="acao" value="incluir">
                    <div class=" mb-3">   
                        <label class="form-label">Nome: </label>
                        <input class="form-control" name="nome"/>
                    </div> 
                    <div class=" mb-3">   
                        <label class="form-label">Quantidade: </label>
                        <input class="form-control" name="quantidade"/>
                    </div>
                    <div class=" mb-3">   
                        <label class="form-label">Preco de Venda: </label>
                        <input class="form-control" name="preco"/>
                    </div>       
                <input class=" btn btn-primary" type="submit" value="Adicionar Produto"/>
                </form>
        <%                    
                    }  
                    } catch(ClassCastException nexc){
                     out.print("<h1>"+nexc.getMessage()+"</h1>");}
        %>
    </body>
</html>
```
<hr>
<h1>Resultados: </h1>
:triangular_flag_on_post: Procedimento 1: https://github.com/Gregdev22/Missao-4-Mundo-3/tree/main/Procedimento%201


https://github.com/Gregdev22/Missao-4-Mundo-3/assets/103840468/2a3c6228-e493-4ab9-aa20-371e317d4f29


<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%201/resultados%20proc1/1%20proc1%20missao%204.png" alt="resultado 1" width="1280" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%201/resultados%20proc1/2%20proc1%20missao%204.png" alt="resultado 2" width="1280" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%201/resultados%20proc1/3%20proc%201%20missao%204.png" alt="resultado 3" width="1280" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%201/resultados%20proc1/4%20proc%201%20missao%204.png" alt="resultado 4" width="1280" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%201/resultados%20proc1/5%20proc%201%20missao%204.png" alt="resultado 5" width="1280" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%201/resultados%20proc1/6%20proc%201%20missao%204.png" alt="resultado 6" width="1280" height="360">
<br>
:triangular_flag_on_post: Procedimento 2: https://github.com/Gregdev22/Missao-4-Mundo-3/tree/main/Procedimento%202


https://github.com/Gregdev22/Missao-4-Mundo-3/assets/103840468/c7a35e84-ac42-4dc6-b901-5df44fd29c98

<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%202/resultados%20proc2/1%20proc%202%20missao%204.png" alt="resultado 1" width="640" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%202/resultados%20proc2/2%20proc2%20missao%204.png" alt="resultado 2" width="640" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%202/resultados%20proc2/3%20proc%202%20missao%204.png" alt="resultado 3" width="640" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%202/resultados%20proc2/4%20proc2%20missao%204.png" alt="resultado 4" width="640" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%202/resultados%20proc2/5%20proc2%20missao%204.png" alt="resultado 5" width="640" height="360">
<img src="https://github.com/Gregdev22/Missao-4-Mundo-3/blob/main/Procedimento%202/resultados%20proc2/6%20proc2%20missao%204.png" alt="resultado 6" width="640" height="360">
<br>
