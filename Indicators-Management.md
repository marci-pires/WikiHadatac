To create a general type of indicator, create a class as a subclass of chear:Indicator. For example, chear:ScienceIndicator rdfs:subClassOf chear:Indicator. If you are using Labkey as a LIMS, this would go under the IndicatorType list.

To create categories within an Indicator Type, create a class as a subclass of that indicator type. For example, chear:Anthropometry rdfs:subClassOf chear:StudyIndicator. If you are using Labkey as a LIMS, this would go under a local list, such as LocalStudyIndicatorType. Study Indicators in particular are used by Hadatac for Study Browsing.

For attributes of a given indicator category, create a class as a subclass of that indicator category. For example, chear:BirthWeight rdfs:subClassOf chear:Anthropometry.

Another important indicator to take note of are Analyte indicators, which show up in the Analyte Browser. For these, you need to create the attributes as subClassOf chear:TargetedAnalyte.