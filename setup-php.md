# setup php

## install

- 事前準備

    ### mac

    - homebrew and settings

        ```
        brew install re2c openssl bison libxml2 autoconf automake icu4c libjpeg libpng libmcrypt krb5 libedit

        echo `export PATH="/usr/local/opt/krb5/bin:$PATH"` >> ~/.zshrc
        echo `export PATH="/usr/local/opt/krb5/sbin:$PATH"` >> ~/.zshrc
        echo `export PKG_CONFIG_PATH="/usr/local/opt/krb5/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.zshrc

        echo `export PATH="/usr/local/opt/openssl@1.1/bin:$PATH"` >> ~/.zshrc
        echo `export PKG_CONFIG_PATH="/usr/local/opt/openssl@1.1/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.zshrc

        echo `export PATH="/usr/local/opt/bzip2/bin:$PATH"` >> ~/.zshrc
        echo `export PHP_BUILD_CONFIGURE_OPTS="--with-bz2=/usr/local/opt/bzip2 --with-iconv=/usr/local/opt/libiconv"` >> ~/.zshrc

        echo `export PATH="/usr/local/opt/icu4c/bin:$PATH"` >> ~/.zshrc
        echo `export PATH="/usr/local/opt/icu4c/sbin:$PATH"` >> ~/.zshrc
        echo `export PKG_CONFIG_PATH="/usr/local/opt/icu4c/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.zshrc

        echo `export PKG_CONFIG_PATH="/usr/local/opt/libedit/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.zshrc

        echo `export PATH="/usr/local/opt/libxml2/bin:$PATH"` >> ~/.zshrc
        echo `export PATH="/usr/local/opt/libxml2/bin:$PATH"` >> ~/.zshrc
        echo `export PKG_CONFIG_PATH="/usr/local/opt/libxml2/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.zshrc

        echo `export PATH="$HOME/.composer/vendor/bin:$PATH"` >> ~/.zshrc
        
        source ~/.zshrc
        ```

    ### redhat

    - install and setting
        
        ```
        sudo yum install ...

        echo `export PATH="/usr/local/opt/krb5/bin:$PATH"` >> ~/.bash_profile
        echo `export PATH="/usr/local/opt/krb5/sbin:$PATH"` >> ~/.bash_profile
        echo `export PKG_CONFIG_PATH="/usr/local/opt/krb5/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.bash_profile

        echo `export PATH="/usr/local/opt/openssl@1.1/bin:$PATH"` >> ~/.bash_profile
        echo `export PKG_CONFIG_PATH="/usr/local/opt/openssl@1.1/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.bash_profile

        echo `export PATH="/usr/local/opt/bzip2/bin:$PATH"` >> ~/.bash_profile
        echo `export PHP_BUILD_CONFIGURE_OPTS="--with-bz2=/usr/local/opt/bzip2 --with-iconv=/usr/local/opt/libiconv"` >> ~/.bash_profile

        echo `export PATH="/usr/local/opt/icu4c/bin:$PATH"` >> ~/.bash_profile
        echo `export PATH="/usr/local/opt/icu4c/sbin:$PATH"` >> ~/.bash_profile
        echo `export PKG_CONFIG_PATH="/usr/local/opt/icu4c/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.bash_profile

        echo `export PKG_CONFIG_PATH="/usr/local/opt/libedit/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.bash_profile

        echo `export PATH="/usr/local/opt/libxml2/bin:$PATH"` >> ~/.bash_profile
        echo `export PATH="/usr/local/opt/libxml2/bin:$PATH"` >> ~/.bash_profile
        echo `export PKG_CONFIG_PATH="/usr/local/opt/libxml2/lib/pkgconfig:$PKG_CONFIG_PATH"` >> ~/.bash_profile

        echo `export PATH="$HOME/.composer/vendor/bin:$PATH"` >> ~/.bash_profile
        
        source ~/.bash_profile
        ```

- homebrew (mac)

    - install and settings

    ```
    brew install php@7.4

    echo `#brew php 7.4.x` >> ~/.zshrc
    echo `export PATH="/usr/local/opt/php@7.4/bin:$PATH"` >> ~/.zshrc
    echo `export PATH="/usr/local/opt/php@7.4/sbin:$PATH"` >> ~/.zshrc

    source ~/.zshrc
    ```

    - check php version

    ```
    php -v
    ```

- phpenv

    - install and settings

    ```
    git clone https://github.com/CHH/phpenv.git
    phpenv/bin/phpenv-install.sh

    echo `# phpenv` >> ~/.zshrc
    echo `if which phpenv > /dev/null; then eval "$(phpenv init -)"; fi` >> ~/.zshrc
    echo `export PATH="$HOME/.phpenv/bin:$PATH"` >> ~/.zshrc

    source ~/.zshrc
    ```

    - install php-build

    ```
    git clone https://github.com/CHH/php-build.git $HOME/.phpenv/plugins/php-build
    ```

    - check install list

    ```
    phpenv install --list
    ```

    - install php version x.x.x

    ```
    phpenv install 7.4.x
    ```

    - target version

    ```
    phpenv versions
    phpenv global 7.4.x / phpenv local 7.4.x
    phpenv rehash
    ```

    - check php version

    ```
    php -v
    ```

- laravel

    - install composer

    ```
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
    php -r "if (hash_file('sha384', 'composer-setup.php') === 'e0012edf3e80b6978849f5eff0d4b4e4c79ff1609dd1e613307e16318854d24ae64f26d17af3ef0bf7cfb710ca74755a') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
    php composer-setup.php
    php -r "unlink('composer-setup.php');"
    ```

    - install laravel and settings

    ```
    composer global require "laravel/installer"

    echo `export PATH="$HOME/.composer/vendor/bin:$PATH"` >> ~/.zshrc
    
    source ~/.zshrc
    ```

    - check laravel

    ```
    laravel -v
    ```

## exec laravel

- local

    ```
    php artisan serve
    ```

## make project (If there is no project)

    ```
    mkdir src

    cd src

    laravel new .
    ```
