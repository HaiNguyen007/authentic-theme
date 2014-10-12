#Authentic
**Authentic** is [Webmin/](https://github.com/webmin/webmin)[Usermin/](https://github.com/webmin/usermin)[Virtualmin](https://www.virtualmin.com/) theme based on [Bootstrap](https://github.com/twbs/bootstrap) and [Font Awesome](https://github.com/FortAwesome/Font-Awesome) that is made with _love_. It uses [CodeMirror](http://codemirror.net/) to highlight config files and show line numbers, when editing manually and [DataTables](http://www.datatables.net/) to add advanced interaction controls to modules' tables. Theme runs using latest releases of dependent software (mentioned above), supporting all in-built modules (even ancient ones) and third-party modules, including [ConfigServer Security & Firewall](http://configserver.com/cp/csf.html).

**Authentic** is fully compatible with latest Webmin 1.710+, Usermin 1.620+ and Virtualmin 4.11+.

##Changelog

####Version 4.1.0 (Oct 12, 2014)
* Changed to using `Switch` rather than `feature qw(switch)` in `index.cgi` and `menu.cgi` to support lower versions of _Perl_
* Changed _View changelog_ `link` in _ConfigServer Security & Firewall_ module to a `button`
* Improved loader animation and behavior
* Added many missing _input_ stylings in some modules
* Fixed `theme_ui_form_end` generator to wrap buttons in _span_ not in _td_, which enables support for lower resolutions. [Issue 4](https://github.com/qooob/authentic-theme/issues/4)
* Added [_German_](https://github.com/qooob/authentic-theme#contributions) translation. Special thanks to _Michael Keck_. [Issue 3](https://github.com/qooob/authentic-theme/issues/3)
* Remove redundant _fonts_ directory

####Version 4.0.0 (Oct 9, 2014)
 * Fixed lost pre-login banner option
 * Added support for _dataTables_. Now you can easily sort table rows based on the table header. It gets easier to manage data in such modules as _Bootup and Shutdown_, _Users and Groups_ and others, containing multi-row data. It also supports _ConfigServer Security & Firewall_, where you can also easily filter _Temporary IP Entries_ and _Listening Ports_
 * Added possibility to use automatic updates for **Authentic Theme**, with direct means of Webmin and its theme installation module - _no other server-side scripts are used_! Updates, when available, will be displayed in *System Information* tab.<br>*Warning!* In order to use automatic updates and check for new theme versions, your system _must have_ the following _Perl_ modules installed: _LWP::Simple_ and _Net::SSLeay_. You should be able to install it from official repos.<br>See [FAQ](https://github.com/qooob/authentic-theme#troubleshoot) for more details
 * Added ability to remove the page _loader_ and see what is happening before the page actually loaded/constructed or just in case of the _loader_ getting stuck. To prematurely remove the _loader_, click on it, using mouse `double-right-click`
 * Removed false dependency for `virtual-server-theme/virtual-server-theme-lib.pl`


>[Complete Changelog](https://github.com/qooob/authentic-theme/blob/master/CHANGELOG.md)

##Update notice

It's very important to clear ___Cache images and files___ in your browser after applying new theme update

##Screenshots

![screenshots](https://rostovtsev.ru/.git/authentic-theme/update_function_screenshot.png)
<hr>
![screenshots](https://rostovtsev.ru/.git/authentic-theme/screenshot-2.0.0.png)

##Principles
* Make the theme fully support all Webmin/Usermin modules
* Be as beautiful, light and easy to use as possible
* Be compatible with mobile devices

##Issues
* Borders on some tables are missing, because of Webmin modules miscalculating _colspan_ values (developers promised to fix it in the near future)
* Few tables go off the grid on small resolutions (< 1000px)

##FAQ
####How do I install _Authentic_ theme?

####Webmin

  To install _Autentic_ theme from repository, just `clone` it into your wherever Webmin binaries folder _(libexec)_ is or [download it directly](https://rostovtsev.ru/.git/authentic-theme/authentic-theme-latest.wbt.gz) and install it going from Webmin:

  `Webmin->Webmin Configuration->Webmin Themes->Install themes->From uploaded file`

####Usermin
  **a)** I recommend to symlink already installed _Authentic_ theme, which will enable you to only update Webmin installation of _Authentic_ not both.

  Creating a symlink as easy as it gets by running as root the following:

  `ln -s /usr/libexec/webmin/authentic-theme /usr/libexec/usermin/authentic-theme`

> The above implies that Webmin binaries on your system are installed under `/usr/libexec/webmin/` and Usermin installation is in `/usr/libexec/usermin/`. The above is true for _CentOS_ and other RHEL distros. You could easily though find out where your installations are by running `/usr/bin/whereis webmin` or `/usr/bin/whereis usermin`.

  **b)** Nevertheless, you could simply install Usermin theme using the same procedure as for Webmin. To install a copy for Usermin go to:

    `Webmin->Usermin Configuration->Usermin Themes->Install themes->From uploaded file`

####Virtualmin
There is no need to take any additional actions. In case _Virtualmin_ module is installed, it will be automatically detected and supported.

###Troubleshoot
> 1. `Can't locate LWP/Simple.pm in @INC (@INC contains: /usr/libexec/webmin..) BEGIN failed--compilation aborted at ..`: <br>
It happens because the theme is trying to load _Perl_ module dependency, that are not installed on your system. `LWP::Simple` - is the simplest and most common type of HTTP request. You can install it using CPAN module in Webmin itself or using CLI and package manager. For example, in RHEL distro you would be able to install it by running<br> `yum install perl-libwww-perl`.
> 2. `Can't locate Net/SSLeay.pm in @INC (@INC contains: ..)`<br>
This happens because Webmin is trying to open a link and download the theme using _https_ protocol. `Net::SSLeay` - is high level functions for accessing web servers (by using HTTP/HTTPS). You can install it using CPAN module in Webmin or using CLI. Package name is `perl-Net-SSLeay`.
> 3. `Can't locate object method "parse" via package "version" (perhaps you forgot to load "version"?) at`. Installing `version` from CPAN, using CPAN module in Webmin will fix this error.

##Contributions

###Translations
* [Michael Keck](https://github.com/mkkeck) (German)

###Code contributions
* [Riccardo Nobile](mailto:riccardo.nobile@winfuture.it)
* [Simone Cragnolini](mailto:simone.cragnolini@winfuture.it)


##Donation

When I started working on this theme, I didn't expect to get any donations  but if you do
_donate_ **it will mean a lot** for _[me](https://rostovtsev.ru)_ and will excite future development.

<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=programming%40rostovtsev%2eru&lc=RU&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHostedGuest">PayPal</a> or <a href="https://money.yandex.ru" alt="41001414241949">Yandex Money: 41001414241949</a>


## License

_Authentic_ is released under the [MIT License][opensource].
[opensource]: http://www.opensource.org/licenses/MIT
