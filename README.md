# OficceSystem
<p class="autoria">
    Por: <a title="Eliel" target="_blank" href="https://github.com/hc3">Eliel</a>
</p>

<h2>
    <font color="#c9040a"> Módulos do Sistema </font>
</h2>
<p align="justify">Cadastor de usuários</p>
<p align="justify">Cadastro de Clientes</p>
<p align="justify">Cadastro de Produtos</p>
<p align="justify">Cadastro de Serviços</p>
<p align="justify">Cadastro de Ordem de Serviços</p>
<p align="justify">Cadastro de Tabelas de Preços</p>


<h3>
    <font color="#c9040a"> Usuários </font>
</h3>
<pre class="prettyprint">
    <code class="lang-bsh">
    'use strict';

    import bcrypt from 'bcrypt-nodejs';
    import mongoose from 'mongoose';

    const Schema = mongoose.Schema;

    const User = {

        name: {
            type:String,
            require:true
        },
        email: {
            type:String,
            require:true
        },
        password: {
            type:String,
            require:true
        }
    };

    const _user = new Schema(User);

    _user.pre('save', (next, done) => {
        let user = this;
        const salt = bcrypt.genSaltSync();

        if(!user.isModified('password')) return next();

        user.password = bcrypt.hashSync(user.password, salt);

        next();
    })

    _user.methods.isPassword = 
        (encodedPassword, password) => bcrypt.compareSync(this.password, encodedPassword);

    export default mongoose.model('User',_user);
    </code>
</pre>

<h3>
    <font color="#c9040a"> Clientes </font>
</h3>
<pre class="prettyprint">
    <code class="lang-bsh">
    {

    }
    </code>
</pre>

<h3>
    <font color="#c9040a"> Produtos </font>
</h3>
<pre class="prettyprint">
    <code class="lang-bsh">
    {
        
    }
    </code>
</pre>

<h3>
    <font color="#c9040a"> Serviços </font>
</h3>
<pre class="prettyprint">
    <code class="lang-bsh">
    {
        
    }
    </code>
</pre>


<h3>
    <font color="#c9040a"> Ordem de Serviço </font>
</h3>
<pre class="prettyprint">
    <code class="lang-bsh">
    {
        
    }
    </code>
</pre>


<h3>
    <font color="#c9040a"> Tabelas de Preços </font>
</h3>
<pre class="prettyprint">
    <code class="lang-bsh">
    {
        
    }
    </code>
</pre>

<h3>
    <font color="#c9040a"> Conteúdo do projeto:</font>
</h3>
<p align="justify">
Projeto vai ter Testes , Gulp ( automatizador de tarefas ), ES6, Babel.
</p>