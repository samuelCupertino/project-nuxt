# About This Project ([video](https://www.instagram.com/p/CaHVBMhOL_s))
<table>
    <tr>
        <td>
          <img src="assets/images/run-toggle-theme.gif" />
        </td>
        <td>
            <h2>Technologies</h2>
            <ul>
                <li>Vue.js</li>
                <li>Nuxt.js</li>
                <li>Atomic Design</li>
                <li>HTML, CSS, JS...</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>
            <h2>Toggle Theme</h2>
            <ul>
                <li>CSS variables</li>
                <li>Local Storage</li>
                <li>JavaScript</li>
            </ul>
        </td>
        <td>
          <img src="assets/images/run-fluid-responsive.gif" />
        </td>
    </tr>
    <tr>
        <td>
          <img src="assets/images/run-infinite-responsive.gif" />
        </td>
        <td>
            <h2>Responsive</h2>
            <ul>
                <li>Fluid Responsive</li>
                <li>Infinite Responsive</li>
                <li>Grid Layout</li>
                <li>Flexible Box Layout</li>
            </ul>
        </td>
    </tr>
</table>

<br/>

<div>
  <h2>Use Case</h2>  
  <p>Este projeto foi idealizado para suprir um contexto de desenvolvimento de uma aplicação v2 (desacoplada e componentizada) compreendendo a necessidade das funcionalidades desenvolvidas serem compartilhadas com a  aplicação v1.<p>
  <p>Neste cenário, o desenvolvimento da aplicação v2 ocorre normalmente. Com tudo, alguns componentes são disponibilizados (em: "page/public-components/ComponentName") com o intuito de serem utilizados na  aplicação v1, por intermédio de um Iframe, onde a uri realiza a requisição do componente, podendo enviar dados (nāo confidenciais, ex: variáveis de estilo, estado inicial...) via GET da aplicação v1 para v2.<p>
  <p>Esta arquitetura foi pensada para atender um projeto de desenvolvimento contínuo, onde parar o desenvolvimento incremental do software, para criar uma nova versão do 0, não é uma opção.<p>
</div>

<br/>

## Start Project 
```bash
# install dependencies
yarn install
```
```bash
# serve with hot reload at localhost:3000
yarn dev
```
