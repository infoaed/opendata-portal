# i18n of https://opendata.riik.ee: scripts, translations, hacks

This is the development repository for implementing multilingual UI support for [Estonian Open Data Portal](https://github.com/opendata-ee), a portal based on CKAN/Drupal integration of [Data.gov.uk portal](https://github.com/datagovuk/dgu-vagrant-puppet). If you are interested where it all started, you can take a look at [this issue from 2014](https://github.com/datagovuk/ckanext-dgu/issues/46).

## Developemnt branches and repositories

The code was forked from relevant repositories of Estonian Open Data Portal. First iteration on default `look_feel_est` branch was to remove hardcoded Estonian translation and replace it with English strings decorated with proper gettext notation. In parallel language switcher and other changes to UI logic were implemented, environment to generate gettext files was prepared, taxonomies and other dynamic content were configures for translation on `i18n_logic` branch. In the end it appeared that changes to live Drupal site never been merged into Feature modules during development of the portal, so this evolved into separate process and was dubbed as `odp_ee_features`. In the end all the branches were merged into `look_feel_est` where the code got its last touch.

### Replace hardcoded Estonian with gettexted English

* https://github.com/opendata-ee/ckanext-dgu/compare/look_feel_est...infoaed:look_feel_est
* https://github.com/opendata-ee/dgu_d7/compare/look_feel_est...infoaed:look_feel_est
* https://github.com/opendata-ee/ckanext-harvest/compare/look_feel_est...infoaed:look_feel_est
* https://github.com/opendata-ee/ckanext-ga-report/compare/look_feel_est...infoaed:look_feel_est
* https://github.com/opendata-ee/ckanext-spatial/compare/look_feel_est...infoaed:look_feel_est

### Language switcher, gettext generation and other i18n logic

* https://github.com/opendata-ee/ckanext-dgu/compare/look_feel_est...infoaed:i18n_logic
* https://github.com/opendata-ee/dgu_d7/compare/look_feel_est...infoaed:i18n_logic
* https://github.com/opendata-ee/shared_dguk_assets/compare/look_feel_est...infoaed:look_feel_est
* https://github.com/opendata-ee/ckan/compare/release-v2.2-dgu...infoaed:release-v2.2-dgu

### Merge live portal changes since 2014 into Drupal Features

* https://github.com/infoaed/dgu_d7/compare/6fd3ffb00e93bb863448f524300904d63406bbc4...odp_ee_features

## Documentation (in Estonian)

* [Install instructions with explanations of the basics of i18n methods](INSTALL.md)
* [General description of the system and evaluation of changes made (and to be done)](docs/README.md)