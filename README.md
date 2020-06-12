*This setup is no longer in use, but I decided to keep it here for posterity.*

# Getting Started

1. Clone the repository
2. You must have PHP and Composer installed.
3. Run `composer install`. This will install all of the needed dependencies, as well as Homestead in `vendor/laravel/homestead` and symlink it to `vendor/bin/homestead`, which we will be aliasing to use Homestead from the project directory.

4. Run `./homestead_init` from the root of the project
5. Edit `/etc/hosts` and add your new domain. The IP address which you should add is by default `192.168.10.10` and the domain is `homestead.app`.

6. If you require a particular package installed on the VM, or if you simply need to do some extra provisioning, you can do it in `~/.homestead/after.sh`
7. Run `homestead up`
    - If you get `"A VirtualBox machine with the name [**name**] already exists..."` then open up VirtualBox and simply delete the machine with the same name. Alternatively you can just change the VM's name in the `Homestead.yaml` file.
    - If bash/zsh gives you `"homestead up command not found"` just source `.shell_aliases` manually.
8. Your app should now be served at `homestead.app` by default. You can also ssh into your homestead box by running `homestead ssh` from the application root.
9. You would have to `homestead ssh` into the homestead VM, `cd` into your project's root folder and run the following commands, in order to have the most recent DB version:
    - `php artisan db:rebuild`
    - `php artisan db:make-tests-dump`
10. The only configuration file you need to care about is located at `~/.homestead/Homestead.yaml`
11. If you need to, you can read up further on configuring Homestead here: https://laravel.com/docs/master/homestead
