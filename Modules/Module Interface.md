# Module Interface

| Methode | Description |
| --- | --- |
| Methods |
| ```init()``` |  |
| ```preLoad()``` |  |
| ```getRouter()``` : ```Router``` |  |
| ```getModules()``` : ```array``` |  |
| ```getTemplate()``` : ```Template```|  |
| ```getCore()``` : ```Core``` |  |
| ```getInstance()``` : ```Module``` |  |
| Module Settings |
| ```setSettings(string $name, mixed $value = NULL)``` |  |
| ```getSettings(string $name, mixed $default = NULL)``` : ```mixed``` |  |
| UI |
| ```addButton(Button \| array $button, bool $logged_in = false)``` |  |
| ```addModal(Modal $modal, bool $logged_in = false)``` | |
| ```assign(string $name, mixed $value)``` | |
| ```url(string $path = '')``` : ```string``` | |
| Hook-System |
| ```addFilter(string $name, Closure \| array  $method, int $priority = 50, bool $logged_in = true)``` : ```bool``` | |
| ```removeFilter(string $name, Closure \| array $method, int $priority = 50)``` : ```bool``` | |
| ```hasFilter(string $name, mixed $method = false)``` : ```bool```  | |
| ```applyFilter(string $name, mixed $arguments)```  : ```mixed``` | |
| ```addAction(string $name, Closure \| array  $method, int $priority = 50, bool $logged_in = true)``` : ```bool``` | |
| ```removeAction(string $name, Closure \| array $method, int $priority = 50)``` : ```bool``` | |
| ```hasAction(string $name, mixed $method = false)``` : ```bool``` | |
| ```runAction(string $name, mixed $arguments = null)``` : ```bool``` | |
