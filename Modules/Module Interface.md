# Module Interface

## General
<details>
  <summary><code class="language-php">init() : void</code></summary>
</details>
<details>
  <summary><code class="language-php">preLoad() : void</code></summary>
</details>

## System
<details>
  <summary><code class="language-php">getRouter() : Router</code></summary>
</details>
<details>
  <summary><code class="language-php">getModules() : array</code></summary>
</details>
<details>
  <summary><code class="language-php">getTemplate() : Template</code></summary>
</details>
<details>
  <summary><code class="language-php">getCore() : Core</code></summary>
</details>
<details>
  <summary><code class="language-php">getInstance() : Module</code></summary>
</details>

## Module Settings
<details>
  <summary><code class="language-php">setSettings(string $name, mixed $value = NULL)</code></summary>
</details>
<details>
  <summary><code class="language-php">getSettings(string $name, mixed $default = NULL) : mixed</code></summary>
</details>

## UI
<details>
  <summary><code class="language-php">addButton(Button | array $button, bool $logged_in = false)</code></summary>
</details>
<details>
  <summary><code class="language-php">addModal(Modal $modal, bool $logged_in = false)</code></summary>
</details>
<details>
  <summary><code class="language-php">assign(string $name, mixed $value)</code></summary>
</details>
<details>
  <summary><code class="language-php">url(string $path = '') : string</code></summary>
</details>

## Hook-System
### Filters
<details>
  <summary><code class="language-php">addFilter(string $name, Closure | array  $method, int $priority = 50, bool $logged_in = true) : bool</code></summary>
</details>
<details>
  <summary><code class="language-php">removeFilter(string $name, Closure | array $method, int $priority = 50) : bool</code></summary>
</details>
<details>
  <summary><code class="language-php">hasFilter(string $name, mixed $method = false) : bool</code></summary>
</details>
<details>
  <summary><code class="language-php">applyFilter(string $name, mixed $arguments) : mixed</code></summary>
</details>

### Actions
<details>
  <summary><code class="language-php">addAction(string $name, Closure | array  $method, int $priority = 50, bool $logged_in = true) : bool</code></summary>
</details>
<details>
  <summary><code class="language-php">removeAction(string $name, Closure | array $method, int $priority = 50) : bool</code></summary>
</details>
<details>
  <summary><code class="language-php">hasAction(string $name, mixed $method = false) : bool</code></summary>
</details>
<details>
  <summary><code class="language-php">runAction(string $name, mixed $arguments) : mixed</code></summary>
</details>
