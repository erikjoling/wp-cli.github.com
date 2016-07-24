---
layout: default
title: Command-line-interface voor WordPress
---

[WP-CLI](https://wp-cli.org/) is een verzameling command-line tools voor het beheren van [WordPress](https://wordpress.org/) installaties. Je kunt plugins updaten, multisite configureren en veel meer, zonder een webbrowser te gebruiken.

Om op de hoogte te blijven, volg [@wpcli op Twitter](https://twitter.com/wpcli) of [schrijf je in voor onze nieuwsbrief](http://wp-cli.us13.list-manage.com/subscribe?u=0615e4d18f213891fc000adfd&id=8c61d7641e).

[![Build Status](https://travis-ci.org/wp-cli/wp-cli.png?branch=master)](https://travis-ci.org/wp-cli/wp-cli) [![Afhankelijkheid Status](https://gemnasium.com/badges/github.com/wp-cli/wp-cli.svg)](https://gemnasium.com/github.com/wp-cli/wp-cli) [![Gemiddelde tijd om een issue op te lossen](http://isitmaintained.com/badge/resolution/wp-cli/wp-cli.svg)](http://isitmaintained.com/project/wp-cli/wp-cli "Gemiddelde tijd om een issue op te lossen") [![Percentage issues die nog open zijn](http://isitmaintained.com/badge/open/wp-cli/wp-cli.svg)](http://isitmaintained.com/project/wp-cli/wp-cli "Percentage issues die nog open zijn")

<div style="
	border: 1px solid #7AD03A;
	-webkit-border-radius: 5px;
	-moz-border-radius: 5px;
	border-radius: 5px;
	padding-left: 10px;
	padding-right: 10px;
">
	<p><strong>A more RESTful WP-CLI</strong> streeft ernaar het potentieel van de WP REST API op de command line te benutten. Het project wordt gesteund door Pressed, Chris Lema, Human Made, Pagely, Pantheon en veel anderen. <a href="https://wp-cli.org/restful/">Meer leren &rarr;</a></p>
</div>

Spring direct naar: [Gebruik](#gebruik) &#124; [Installeren](#installeren) &#124; [Support](#support) &#124; [Uitbreiden](#uitbreiden) &#124; [Bijdragen](#bijdragen) &#124; [Credits](#credits)

## Gebruik

Het doel van WP-CLI is het bieden van een command-line-interface voor elke handeling die je zou willen uitvoeren in de WordPress admin. Met `wp plugin install --activate` ([doc](https://wp-cli.org/commands/plugin/install/)) kan je bijvoorbeeld een WordPress plugin installeren en activeren:

```
$ wp plugin install rest-api --activate
Installing WordPress REST API (Version 2) (2.0-beta13)
Downloading install package from https://downloads.wordpress.org/plugin/rest-api.2.0-beta13.zip...
Unpacking the package...
Installing the plugin...
Plugin installed successfully.
Activating 'rest-api'...
Success: Plugin 'rest-api' activated.
```

Met WP-CLI kun je ook opdrachten uitvoeren die niet mogelijk zijn in de WordPress admin. Met `wp transient delete-all` ([doc](https://wp-cli.org/commands/transient/delete-all/)) kun je bijvoorbeeld één of alle transients verwijderen:

```
$ wp transient delete-all
Success: 34 transients deleted from the database.
```

Voor een uitgebreidere introductie over hoe WP-CLI te gebruiken, lees [Quick Start guide](https://wp-cli.org/docs/quick-start/).

Voel je je al vertrouwd met de basis? Ga dan naar de [complete lijst van opdrachten](https://wp-cli.org/commands/) voor meer details over het beheren van thema's en plugins, het importeren en exporteren van data, het uitvoeren van database zoek-en-vervang taken en meer.

## Installeren

Het downloaden van het Phar bestand is onze aangeraden installatiemethode. Mocht het nodig zijn, dan kun je ook onze documentatie lezen over [alternatieve installatiemethodes](https://wp-cli.org/docs/installing/).

Voordat je WP-CLI installeert, zorg er eerst voor dat je omgeving voldoet aan de minimum eisen:

- UNIX-achtige omgeving (OS X, Linux, FreeBSD, Cygwin); beperkte ondersteuning in Windows omgeving
- PHP 5.3.29 of hoger
- WordPress 3.7 of hoger

Als je voldoet aan de eisen kun je het [wp-cli.phar](https://raw.github.com/wp-cli/builds/gh-pages/phar/wp-cli.phar) bestand downloaden via `wget` of `curl`: 

```
$ curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
```

Vervolgens kijk je of het werkt:

```
$ php wp-cli.phar --info
```

Om WP-CLI vanaf de command-line te kunnen gebruiken door `wp` te typen, maak je het bestand uitvoerbaar en zet het ergens in je PATH. Bijvoorbeeld:

```
$ chmod +x wp-cli.phar
$ sudo mv wp-cli.phar /usr/local/bin/wp
```

Als WP-CLI goed is geïnstalleerd zou je ongeveer het volgende moeten zien wanneer je `wp --info` uitvoert`:

```
$ wp --info
PHP binary:    /usr/bin/php5
PHP version:    5.5.9-1ubuntu4.14
php.ini used:   /etc/php5/cli/php.ini
WP-CLI root dir:        /home/wp-cli/.wp-cli
WP-CLI packages dir:    /home/wp-cli/.wp-cli/packages/
WP-CLI global config:   /home/wp-cli/.wp-cli/config.yml
WP-CLI project config:
WP-CLI version: 0.23.0
```

### Bijwerken

Je kunt WP-CLI bijwerken met `wp cli update` ([doc](https://wp-cli.org/commands/cli/update/)), of door de installatie opnieuw uit te voeren.

Ben je in een avontuurlijke bui? Voer dan `wp cli update --nightly` uit om de meest recente nightly build van WP-CLI binnen te halen. De nightly build is min of meer stabiel genoeg om te gebruiken in je ontwikkelomgeving en bevat de nieuwste en tofste WP-CLI features.

### Tab-aanvulling

WP-CLI wordt ook geleverd met een tab-aanvullingsscript voor Bash en ZSH. Download eenvoudig [wp-completion.bash](https://github.com/wp-cli/wp-cli/raw/master/utils/wp-completion.bash) en verwijs ernaar in je `~/.bash_profile`:

```
source /FULL/PATH/TO/wp-completion.bash
```

Vergeet naderhand niet om `source ~/.bash_profile` uit te voeren.

## Support

De beheerders en bijdragers van WP-CLI doen hun best tijdelijk te reageren op alle nieuwe issues. Om optimaal gebruik te maken van hun vrijwillige inspanningen, kijk eerst of er eventueel een antwoord is op je vraag in één van de volgende bronnen:

- [Veel voorkomende problemen en hun oplossingen](https://wp-cli.org/docs/common-issues/)
- [Hoe dien ik een bug rapport in](https://wp-cli.org/docs/bug-reports/)
- [Documentatieportaal](https://wp-cli.org/docs/)
- [Open of gesloten issues op GitHub](https://github.com/wp-cli/wp-cli/issues?utf8=%E2%9C%93&q=is%3Aissue)
- [WordPress StackExchange forums](http://wordpress.stackexchange.com/questions/tagged/wp-cli)

Als je antwoord niet tussen één van de bestaande bronnen staat, voel je dan vrij [een issue aan te maken](https://github.com/wp-cli/wp-cli/issues/new) met je vraag.

Stel je vragen alsjeblieft niet via Twitter. Twitter is geen geschikt kanaal voor ondersteuning omdat: 1) het lastig is om gesprekken te voeren van minder dan 140 karakters, en 2) op Twitter kunnen mensen met eenzelfde vraag het antwoord niet zoeken in eerder gevoerde gesprekken.

Als je een WordPress.org account hebt kun je ook overwegen deel te nemen aan het `#cli` kanaal op [WordPress.org Slack organization](https://make.wordpress.org/chat/).

## Uitbreiden

Een **opdracht** is een atoom in de WP-CLI functionaliteit. `wp plugin install` ([doc](https://wp-cli.org/commands/plugin/install/)) is één opdracht. `wp plugin activate` ([doc](https://wp-cli.org/commands/plugin/activate/)) een andere.

WP-CLI ondersteunt het registreren van elke aanroepbare class, functie of closure als een opdracht. Gebruiksdetails worden gelezen van de callbacks PHPdoc. `WP_CLI::add_command()` ([doc](https://wp-cli.org/docs/internal-api/wp-cli-add-command/)) wordt gebruikt voor registreren van opdrachten, zowel intern als voor third-party doeleinden. 

```
/**
 * Delete an option from the database.
 *
 * Returns an error if the option didn't exist.
 *
 * ## OPTIONS
 *
 * <key>
 * : Key for the option.
 *
 * ## EXAMPLES
 *
 *     $ wp option delete my_option
 *     Success: Deleted 'my_option' option.
 */
$delete_option_cmd = function( $args ) {
	list( $key ) = $args;

	if ( ! delete_option( $key ) ) {
		WP_CLI::error( "Could not delete '$key' option. Does it exist?" );
	} else {
		WP_CLI::success( "Deleted '$key' option." );
	}
};
WP_CLI::add_command( 'option delete', $delete_option_cmd );
```

WP-CLI omvat een groot aantal opdrachten. Het is makkelijker dan het er uit ziet een custom WP-CLI opdracht aan te maken. Lees het [commando kookboek](https://wp-cli.org/docs/commands-cookbook/) om er meer over te leren. Browse de [interne API docs](https://wp-cli.org/docs/internal-api/) om een verscheidenheid aan nuttige functies te ontdekken die je kan gebruiken in je custom WP-CLI opdracht.

## Bijdragen

Welkom en bedankt!

Wij waarderen het dat je initiatief toont bij te dragen aan WP-CLI. Het is dankzij jou, en de gemeenschap om jou heen, dat WP-CLI zo'n geweldig project is.

**Bijdragen is niet beperkt tot code.** Wij moedigen je aan bij te dragen op een manier die het beste bij je vaardigheden past; tutorials schrijven, een demo geven bij een lokale meetup, andere helpen met support vragen, of het herschrijven van onze documentatie.

Neem even de tijd om [de richtlijnen goed door te nemen](https://wp-cli.org/docs/contributing/). Het volgen van de richtlijnen helpt communiceren dat je de tijd van andere bijdragers aan het project respecteert. Omgekeerd zullen zij ook hun best doen dit respecteren wanneer ze met je werken, in verschillende tijdzones en over de hele wereld.

## Leiderschap

WP-CLI wordt geleid door deze individuen:

* [Daniel Bachhuber](https://github.com/danielbachhuber/) - huidige beheerder
* [Cristi Burcă](https://github.com/scribu) - vorige beheerder
* [Andreas Creten](https://github.com/andreascreten) - oprichter

Lees meer over het [projectbeleid](https://wp-cli.org/docs/governance/) en bekijk een [volledige lijst bijdragers](https://github.com/wp-cli/wp-cli/contributors).

## Credits

Naast de bibliotheken gedefinieerd in [composer.json](composer.json) hebben we code of ideeën gebruikt van de volgende projecten: 

* [Drush](http://drush.ws/) voor... veel dingen
* [wpshell](http://code.trac.wordpress.org/browser/wpshell) voor `wp shell`
* [Regenerate Thumbnails](http://wordpress.org/plugins/regenerate-thumbnails/) voor `wp media regenerate`
* [Search-Replace-DB](https://github.com/interconnectit/Search-Replace-DB) voor `wp search-replace`
* [WordPress-CLI-Exporter](https://github.com/Automattic/WordPress-CLI-Exporter) voor `wp export`
* [WordPress-CLI-Importer](https://github.com/Automattic/WordPress-CLI-Importer) voor `wp import`
* [wordpress-plugin-tests](https://github.com/benbalter/wordpress-plugin-tests/) voor `wp scaffold plugin-tests`
