<style>
  .demo-box {
    .el-dropdown {
      vertical-align: top;
    
      & + .el-dropdown {
        margin-left: 15px;
      }
    }
    .el-dropdown-link {
      cursor: pointer;
      color: #409EFF;
    }
    .el-icon-arrow-down {
      font-size: 12px;
    }
  }

  .block-col-2 {
    margin: -24px;

    .el-col {
      padding: 30px 0;
      text-align: center;
      border-right: 1px solid #eff2f6;
    
      &:last-child {
        border-right: 0;
      }
    }
  }

 .demo-dropdown .demonstration {
   display: block;
   color: #8492a6;
   font-size: 14px;
   margin-bottom: 20px;
 }
</style>

<script>
  export default {
    methods: {
      handleClick() {
        alert('button click');
      },
      handleCommand(command) {
        this.$message('click on item ' + command);
      }
    }
  }
</script>
## Dropdown
Menú conmutable para visualizar listas de enlaces y acciones.

### Uso básico
Pase el ratón por el menú desplegable para desplegarlo y obtener más acciones.

:::demo El elemento desencadenante se representa con el slot predeterminado, y la parte desplegable se representa con el slot llamado dropdown. Por defecto, la lista desplegable se muestra cuando se pasa el ratón por encima del elemento desencadenante sin necesidad de hacer clic en él.

```html
<af-dropdown>
  <span class="af-dropdown-link">
    Dropdown List<i class="af-icon-arrow-down el-icon--right"></i>
  </span>
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item disabled>Action 4</af-dropdown-item>
    <af-dropdown-item divided>Action 5</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<style>
  .el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
</style>

```

:::

### Elemento detonante

Utilizando un botón para activar la lista desplegable.

:::demo Utilice `split-button` para dividir el elemento detonante en un grupo de botones, siendo el botón izquierdo un botón normal y el botón derecho el objetivo real de la detonacion. Si desea insertar una línea de separación entre la posición tres y la posición cuatro, sólo añada un divisor de clase a la posición cuatro.

```html
<af-dropdown>
  <af-button type="primary">
    Dropdown List<i class="af-icon-arrow-down el-icon--right"></i>
  </af-button>
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item>Action 4</af-dropdown-item>
    <af-dropdown-item>Action 5</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>
<af-dropdown split-button type="primary" @click="handleClick">
  Dropdown List
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item>Action 4</af-dropdown-item>
    <af-dropdown-item>Action 5</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<style>
  .el-dropdown {
    vertical-align: top;
  }
  .el-dropdown + .el-dropdown {
    margin-left: 15px;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
</style>

<script>
  export default {
    methods: {
      handleClick() {
        alert('button click');
      }
    }
  }
</script>
```
:::

### Cómo detonar el evento

Haga clic en el elemento detonante o sobre él.

:::demo Utilice el atributo `trigger`. Por defecto, es `hover`.

```html
<af-row class="block-col-2">
  <af-col :span="12">
    <span class="demonstration">hover to trigger</span>
    <af-dropdown>
      <span class="af-dropdown-link">
        Dropdown List<i class="af-icon-arrow-down el-icon--right"></i>
      </span>
      <af-dropdown-menu slot="dropdown">
        <af-dropdown-item>Action 1</af-dropdown-item>
        <af-dropdown-item>Action 2</af-dropdown-item>
        <af-dropdown-item>Action 3</af-dropdown-item>
        <af-dropdown-item>Action 4</af-dropdown-item>
        <af-dropdown-item>Action 5</af-dropdown-item>
      </af-dropdown-menu>
    </af-dropdown>
  </af-col>
  <af-col :span="12">
    <span class="demonstration">click to trigger</span>
    <af-dropdown trigger="click">
      <span class="af-dropdown-link">
        Dropdown List<i class="af-icon-arrow-down el-icon--right"></i>
      </span>
      <af-dropdown-menu slot="dropdown">
        <af-dropdown-item>Action 1</af-dropdown-item>
        <af-dropdown-item>Action 2</af-dropdown-item>
        <af-dropdown-item>Action 3</af-dropdown-item>
        <af-dropdown-item>Action 4</af-dropdown-item>
        <af-dropdown-item>Action 5</af-dropdown-item>
      </af-dropdown-menu>
    </af-dropdown>
  </af-col>
</af-row>

<style>
  .el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
  .demonstration {
    display: block;
    color: #8492a6;
    font-size: 14px;
    margin-bottom: 20px;
  }
</style>
```
:::

### Ocultamiento del menú

Use `hide-on-click` para definir si el menú se cierra al hacer clic.

:::demo El menú predeterminado se cerrará cuando haga clic en los elementos del menú, y se puede desactivar configurando `hide-on-click` como false.

```html
<af-dropdown :hide-on-click="false">
  <span class="af-dropdown-link">
    Dropdown List<i class="af-icon-arrow-down el-icon--right"></i>
  </span>
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item disabled>Action 4</af-dropdown-item>
    <af-dropdown-item divided>Action 5</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<style>
  .el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
</style>
```
:::

### Evento command

Al hacer clic en cada elemento desplegable se detona un evento cuyo parámetro es asignado por cada elemento.

:::demo
```html
<af-dropdown @command="handleCommand">
  <span class="af-dropdown-link">
    Dropdown List<i class="af-icon-arrow-down el-icon--right"></i>
  </span>
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item command="a">Action 1</af-dropdown-item>
    <af-dropdown-item command="b">Action 2</af-dropdown-item>
    <af-dropdown-item command="c">Action 3</af-dropdown-item>
    <af-dropdown-item command="d" disabled>Action 4</af-dropdown-item>
    <af-dropdown-item command="e" divided>Action 5</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<style>
  .el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
</style>

<script>
  export default {
    methods: {
      handleCommand(command) {
        this.$message('click on item ' + command);
      }
    }
  }
</script>
```
:::

### Tamaños

Además del tamaño predeterminado, el componente Dropdown proporciona tres tamaños adicionales para que pueda elegir entre diferentes escenarios

:::demo Utilice el atributo `size` para establecer tamaños adicionales con `medium`, `small` o `mini`.

```html
<af-dropdown split-button type="primary">
  Default
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item>Action 4</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<af-dropdown size="medium" split-button type="primary">
  Medium
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item>Action 4</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<af-dropdown size="small" split-button type="primary">
  Small
  <af-dropdown-menu slot="dropdown">
   <af-dropdown-item>Action 1</af-dropdown-item>
   <af-dropdown-item>Action 2</af-dropdown-item>
   <af-dropdown-item>Action 3</af-dropdown-item>
   <af-dropdown-item>Action 4</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>

<af-dropdown size="mini" split-button type="primary">
  Mini
  <af-dropdown-menu slot="dropdown">
    <af-dropdown-item>Action 1</af-dropdown-item>
    <af-dropdown-item>Action 2</af-dropdown-item>
    <af-dropdown-item>Action 3</af-dropdown-item>
    <af-dropdown-item>Action 4</af-dropdown-item>
  </af-dropdown-menu>
</af-dropdown>
```
:::


### Dropdown atributos
| Atributo      | Descripción                              | Tipo    | Valores aceptados                        | Por defecto |
| ------------- | ---------------------------------------- | ------- | ---------------------------------------- | ----------- |
| type          | tipo de botón de menú, consulte Componente`Button`, sólo funciona cuando `split-button` es true. | string  | —                                        | —           |
| size          | tamaño del menú, también funciona en `split-button` | string  | medium / small / mini                    | —           |
| split-button  | si se visualiza un grupo de botones      | boolean | —                                        | false       |
| placement     | colocación del menú                      | string  | top/top-start/top-end/bottom/bottom-start/bottom-end | bottom-end  |
| trigger       | cómo detonar                             | string  | hover/click                              | hover       |
| hide-on-click | si se oculta el menú después de hacer clic en el elemento | boolean | —                                        | true        |
| show-timeout  | Tiempo de retardo antes de mostrar un dropdown (solamente trabaja cuando se dispara `hover`) | number  | —                                        | 250         |
| hide-timeout  | Tiempo de retardo antes de ocultar un dropdown (solamente trabaja cuando se dispara `hover`) | number  | —                                        | 150         |

### Dropdown Slots

| Nombre | Descripción |
|------|--------|
| — | content of Dropdown. Notice: Must be a valid html dom element (ex. `<span>, <button> etc.`) or `el-component`, to attach the trigger listener  |
| dropdown | content of the Dropdown Menu, usually a `<af-dropdown-menu>` element |

### Dropdown Eventos
| Nombre         | Descripción                              | Parametros                               |
| -------------- | ---------------------------------------- | ---------------------------------------- |
| click          | si `split-button` es `true`, se activa al hacer clic en el botón izquierdo | —                                        |
| command        | activa cuando se hace clic en un elemento desplegable | el comando enviado desde el elemento desplegable |
| visible-change | se activa cuando aparece/desaparece el desplegable | true cuando aparece, y false de otro modo |

### Dropdown Menu Item Atributos
| Atributo | Descripción                              | Tipo                 | Valores aceptados | Por defecto |
| -------- | ---------------------------------------- | -------------------- | ----------------- | ----------- |
| command  | un comando que se enviará al `command` callback del Dropdown | string/number/object | —                 | —           |
| disabled | si el elemento está desactivado          | boolean              | —                 | false       |
| divided  | si se visualiza un divisor               | boolean              | —                 | false       |
