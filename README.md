# LaravelUp
Local Dev Environment

## Prerequisites

Be sure to have Vagrant installed in the manner that best suits you and your computer, which some might say is an extension of you. (I wouldn't say that, though.)

## Installation

```sh
# Step 1
# cd into the LaravelUp project directory and run the following:
./bin/install {PROJECT_NAME}

# Note that the PROJECT_NAME must be a string containing only the
# following characters `a-z0-9_.-`, must start with a letter and
# end with a non-special character. (Sorry, them's the breaks.)

# Step 2
# Try to vagrant up and shell onto the box
vagrant up && vagrant ssh

# Step 3
# Wait for the box to boot up, jump on that bad boy and run the following:
cd code && composer install

# Step 4
# Once that's done, open your favorite browser and visit:
http://{PROJECT_NAME}.local
```

## Shutdown

```sh
vagrant halt
```

## A Brief Note on PHP Version Discrepancies

After running composer install on the virtual machine, you'll have a number of PHP 7 dependencies which might cause issues when trying to shut down your vagrant box later. Vagrant only needs some dependencies in the vendor/laravel/homestead stuff so it shouldn't be an issue, BUT if it is run the following:

```sh
./bin/panic
```

This will reinstate the initial Homestead dependencies so you can at least run `vagrant halt` and `vagrant destroy` before you throw this project in the trash because it almost made you lock precious machine resources in a digital prison (or at least open the VirtualBox GUI, gross).
