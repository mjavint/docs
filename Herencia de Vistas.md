# Trabajo con el XPath de Odoo

`view1.xml`

```xml
    <record id="view1_form" model="ir.ui.view">
        <field name="name">view_form</field>
        <field name="model">model.name</field>
        <field name="arch" type="xml">
            <div class="settings">
                <page name="Usuario" string="User">
                    <field name="user_ids"/>
                </page>
            </div>
        </field>
    </record>
```

`view_inherit.xml`self.env.ref('view1_form_inherit')

```xml
<record id="view1_form_inherit" model="ir.ui.view">
    <field name="name">view_inherit</field>
    <field name="model">model.name</field>
    <field name="inherit_id" ref="addon_name.view1_form"/>
    <field name="arch" type="xml">
        <!-- Elementos dentro del recuperado no importa el orden -->
        <xpath expr="//div[hasClass('settings')]" position="inside">
            <p>Esto es un elemento dentro de los div con clase settings<p/>
        </xpath>

        <!-- Elementos en posicion antes -->
        <xpath expr="//page[@name='Usuario']]" position="before">
            <p>Esto es un elemento dentro de los div con clase settings<p/>
        </xpath>

         <!-- Elementos en posicion despues -->
        <xpath expr="//page[@name='Usuario']]" position="after">
            <p>Esto es un elemento dentro de los div con clase settings<p/>
        </xpath>

        <!-- Accede a los atributos y los modifica -->
        <xpath expr="//field[@name='user_ids']" position="attributes">
            <attribute name="invisible">1</attribute>
            <attribute name="string">Usuario</attribute>
        </xpath>

        <field name="user_ids" position="attributes">
            <attribute name="invisible">1</attribute>
            <attribute name="string">Usuario</attribute>
        <field/>

        <!-- Reemplaza los elementos que contiene por el nuevo -->
        <xpath expr="//div[hasClass('settings')]" position="replace">
            <p>Esto es un elemento dentro de los div con clase settings<p/>
        </xpath>
    </field>
</record>
```
