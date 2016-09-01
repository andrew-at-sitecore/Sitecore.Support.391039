# Sitecore.Support.391039
Ensures that Sitecore works smoothly even when Solr server or one of Solr cores are not available. Periodically retries to establish connection to Solr. Does not try to execute a search query if connection is not established which allows to avoid performance degradation. Alternative reference number is 94024.

## Main

This repository contains Sitecore Patch #391039, which extends the default `Sitecore.ContentSearch.SolrProvider.SolrSearchIndex` and `Sitecore.ContentSearch.SolrProvider.SwitchOnRebuildSolrSearchIndex` to handle unavailability of Solr server.

## Deployment

To apply the patch on either CM or CD server perform the following steps:

1. Place the `Sitecore.Support.391039.dll` assembly into the `\bin` directory.
2. Place the `Sitecore.Support.391039.config` file into the `\App_Config\Include` directory.
3. In configuration files find all occurrences of 
`Sitecore.ContentSearch.SolrProvider.SolrSearchIndex, Sitecore.ContentSearch.SolrProvider`
and replace them with
`Sitecore.Support.ContentSearch.SolrProvider.SolrSearchIndex, Sitecore.Support.391039`
4. In configuration files find all occurrences of
`Sitecore.ContentSearch.SolrProvider.SwitchOnRebuildSolrSearchIndex, Sitecore.ContentSearch.SolrProvider`
and replace them with
`Sitecore.Support.ContentSearch.SolrProvider.SwitchOnRebuildSolrSearchIndex, Sitecore.Support.391039`

## Content 

Sitecore Patch includes the following files:

1. `\bin\Sitecore.Support.391039.dll`
2. `\App_Config\Include\x.Sitecore.Support.391039\Sitecore.Support.391039.config` - definitions for SolrStatusMonitor component
3. `\App_Config\Include\x.Sitecore.Support.391039\Sitecore.Support.391039.IndexDefinitions.config.example` - template configuration file to configure Solr indexes 
4. `\App_Config\Include\x.Sitecore.Support.391039\Sitecore.Support.391039.SwitchOnRebuild.IndexDefinitions.config.example` - template configuration file to configure SwitchOnRebuild Solr indexes 

## License

This patch is licensed under the [Sitecore Corporation A/S License](LICENSE).

## Download

Downloads are available via [GitHub Releases](https://github.com/SitecoreSupport/Sitecore.Support.391039/releases).
