Symfony Console GitHub Action
=============================

## Usage

You can use it as a Github Action like this:

```yaml
# .github/workflows/lint.yml
name: "Lint"

on:
  pull_request:
  push:

jobs:
  merge:
    name: "Lint symfony container"
    
    runs-on: "ubuntu-latest"

    steps:
    - name: "Checkout"
      uses: "actions/checkout@v2"
      
    - name: "Install PHP with extensions"
      uses: "shivammathur/setup-php@v2"
        
    - name: "Install Composer dependencies"
      uses: "ramsey/composer-install@v2"
      
    - name: "Lint"
      uses: "nucleos/symfony-console-action@1.0.0"
      env:
        kernel: "App\\CustomKernel"
        command: "lint:container"
```

The ``kernel`` environment is optional. The default is `App\Kernel`.
