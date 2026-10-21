<p align="center">
  <a href="https://github.com/mzStack"><img src="https://raw.githubusercontent.com/mzStack/.github/main/assets/images/mzstack-logo-horizontal.svg" alt="mzStack" width="360"></a>
</p>

<p align="center">
  <a href="https://github.com/mzStack"><img alt="GitHub: mzStack" src="https://img.shields.io/badge/GitHub-mzStack-181717?logo=github&amp;logoColor=white"></a>
  <img alt="Specification 0.0.0, Working Draft" src="https://img.shields.io/badge/spec-0.0.0%20%C2%B7%20Working%20Draft-023E8A">
  <a href="https://github.com/mzStack/.github/blob/main/CODE_OF_CONDUCT.md"><img alt="Code of conduct: read" src="https://img.shields.io/badge/Code%20of%20conduct-read-007EC6"></a>
</p>

## Overview

_mzStack_ is a framework for **storing, querying and visualising large-scale mass spectrometry datasets**. Development currently focuses on **mass spectrometry-based metabolomics**, and we welcome community input on extending mzStack to **proteomics** and other mass spectrometry applications.

mzStack is designed to bring mass spectrometry data together in **queryable datasets**. The aim is to make it easier to analyse and compare data from different acquisition runs and datasets. It uses [Apache Parquet](https://parquet.apache.org/) for columnar data storage. With suitable query engines, analysis can run without loading the whole dataset into memory.

The **mzStack specification** defines how datasets are organised, how queries and plots are interpreted, and how processed results link back to the data from which they were derived. The **Python and R reference implementations** put this specification into practice. They provide libraries for **building web and other interactive applications** to browse datasets, query spectra and visualise mass spectrometry data.

mzStack builds on [community standards, software and repositories](#community-standards-software-and-repositories) developed and maintained by the wider scientific community, particularly the proteomics and metabolomics communities. This work would not be possible without [these community efforts and direct or indirect funding](#funding-and-acknowledgements).

## Development status and early access

**mzStack is under active development.** The specification remains a working draft. The Python and R reference implementations and associated applications are evolving alongside it. Interfaces and functionality may change, and users may encounter bugs or unexpected behaviour.

**The specification and reference implementation repositories are temporarily private while we prepare their initial public release and supporting documentation.**

Please [contact us](#get-involved) to **request early access, discuss ideas or explore ways to get involved**.

## Community standards, software and repositories

mzStack builds on existing community standards, software and open data repositories.

**Our aim is to complement the tools and workflows researchers already use, drawing on established standards, formats and conventions to make data easier to exchange and reuse.**

We welcome contributions that help mzStack adopt additional standards, work with more tools and data repositories, or support new use cases. If there are other standards, software tools or data repositories we should consider, please [let us know](#get-involved).

### FAIR principles

- The mzStack specification is designed to support the [FAIR](https://www.go-fair.org/fair-principles/) (**Findable, Accessible, Interoperable and Reusable**) principles where applicable.

### Standards, formats and vocabularies

The mzStack specification draws on the following community standards, formats and vocabularies.

<table>
  <thead>
    <tr>
      <th scope="col" align="left">Category</th>
      <th scope="col" align="left">Resource / Standard</th>
      <th scope="col" align="left">Purpose</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="rowgroup" rowspan="2" align="left" valign="top">Acquisition data</th>
      <td><a href="https://www.psidev.info/mzML">mzML</a></td>
      <td>A standard format for mass spectrometry data.</td>
    </tr>
    <tr>
      <td><a href="https://www.psidev.info/mzpeak">mzPeak</a></td>
      <td>A format for storing mass spectrometry runs.</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th scope="rowgroup" rowspan="3" align="left" valign="top">Results and spectral formats</th>
      <td><a href="https://www.psidev.info/mztab-specifications">mzTab-M</a> and <a href="https://www.psidev.info/mztab-specifications">mzTab</a></td>
      <td>mzTab-M is a standard for reporting metabolomics results, developed from the mzTab format used in proteomics.</td>
    </tr>
    <tr>
      <td><a href="https://github.com/HUPO-PSI/mzSpecLib">mzSpecLib</a></td>
      <td>A standard for representing and exchanging spectral libraries.</td>
    </tr>
    <tr>
      <td><a href="https://www.matrixscience.com/help/data_file_help.html">MGF</a> and <a href="https://chemdata.nist.gov/mass-spc/ms-search/docs/Ver20Man_11.pdf">MSP</a></td>
      <td>Widely used text formats for exchanging peak lists (MGF) and spectral library entries (MSP).</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th scope="rowgroup" rowspan="3" align="left" valign="top">Metadata, identifiers and vocabularies</th>
      <td><a href="https://isa-specs.readthedocs.io/">ISA-Tab</a></td>
      <td>A community format for describing studies, samples and their relationships to data files.</td>
    </tr>
    <tr>
      <td><a href="https://www.psidev.info/usi">Universal Spectrum Identifier (USI)</a></td>
      <td>A standardised way to identify and reference individual mass spectra. See the <a href="https://ccms-ucsd.github.io/GNPSDocumentation/usi/">GNPS metabolomics documentation</a> for its use in metabolomics.</td>
    </tr>
    <tr>
      <td><a href="https://github.com/HUPO-PSI/psi-ms-CV">PSI-MS controlled vocabulary</a> and <a href="https://obofoundry.org/ontology/uo.html">Units of Measurement Ontology (UO)</a></td>
      <td>Shared terms for describing mass spectrometry data and measurement units.</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th scope="rowgroup" rowspan="2" align="left" valign="top">Storage and data exchange</th>
      <td><a href="https://parquet.apache.org/">Apache Parquet</a></td>
      <td>An open columnar file format for efficient data storage.</td>
    </tr>
    <tr>
      <td><a href="https://arrow.apache.org/">Apache Arrow</a></td>
      <td>A standardised columnar format for representing data in memory and exchanging it between systems.</td>
    </tr>
  </tbody>
</table>

### Software

- **Columnar data storage and access:** [Apache Arrow](https://arrow.apache.org/) provides libraries for working with columnar data across programming languages, including reading and writing [Parquet](https://parquet.apache.org/) files.
- **Query languages and engines:** [MassQL](https://www.nature.com/articles/s41592-025-02660-z) provides a query language for mass spectrometry data. [DuckDB](https://duckdb.org/) provides a SQL query engine.
- **Study and metadata management:** [mtblspy](https://github.com/EBI-Metabolights/mtblspy) provides a Python command-line interface for managing MetaboLights studies and ISA-Tab metadata.
- **[R for Mass Spectrometry ecosystem](https://www.rformassspectrometry.org/):** A collection of R packages designed to work together for mass spectrometry data processing and analysis. [Spectra](https://bioconductor.org/packages/Spectra) provides infrastructure for handling spectra. Related tools include [MsBackendParquet](https://github.com/computational-metabolomics/MsBackendParquet) for Parquet-backed data access, [lcmsPlot](https://bioconductor.org/packages/lcmsPlot) for visualisation and [SpectraQL](https://bioconductor.org/packages/SpectraQL) for MassQL queries within Spectra.

### Open data repositories

- **[MetaboLights](https://www.ebi.ac.uk/metabolights/):** An open data repository for metabolomics studies, bringing together experimental data and associated metadata. It uses community formats such as [mzML](https://www.psidev.info/mzML) for mass spectrometry data and [ISA-Tab](https://isa-specs.readthedocs.io/) for study and sample descriptions.

## mzStack repositories

The following repositories belong to the [mzStack organisation](https://github.com/mzStack). They are temporarily private while we prepare their initial public release.

Please [contact us](#get-involved) to **request early access, discuss ideas or explore ways to get involved**.

| Repository | Contents |
| --- | --- |
| mzstack-spec | The mzStack specification. |
| mzstack-py | The Python reference implementation. |
| mzstack-r | The R reference implementation. |
| mzstack-apps | Web and other interactive applications built on the Python and R reference implementations. |

## Get involved

Our long-term aim is to build and sustain mzStack as a community-driven effort. Our initial work is a starting point, and we welcome use cases, feedback and contributions to the specification, reference implementations, testing and documentation.

Please contact us directly to **request early access, discuss ideas or explore ways to get involved:**

- **Ralf Weber** ([University of Birmingham](https://www.birmingham.ac.uk/), UK): [GitHub](https://github.com/computational-metabolomics) · [r.j.weber@bham.ac.uk](mailto:r.j.weber@bham.ac.uk)
- **Ossama Edbali** ([University of Birmingham](https://www.birmingham.ac.uk/), UK): [o.edbali@bham.ac.uk](mailto:o.edbali@bham.ac.uk)

See our [contribution guide](https://github.com/mzStack/.github/blob/main/CONTRIBUTING.md) for ways to participate. All mzStack repositories and community spaces are covered by our [Code of Conduct](https://github.com/mzStack/.github/blob/main/CODE_OF_CONDUCT.md).

## Funding and acknowledgements

**We thank the researchers, developers and data curators who develop and maintain the standards, software and open data repositories on which mzStack builds.** We are also grateful to everyone who has shared feedback and suggestions to date.

The initial development of mzStack has benefited from direct or indirect support from the [European Union's Horizon 2020 programme](https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-2020_en) ([PrecisionTox](https://precisiontox.org/project/), grant agreement No. **965406**), [BioFAIR Pathfinder](https://biofair.uk/) and [ELIXIR](https://elixir-europe.org/).

<p align="center">
  <a href="https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-2020_en"><img src="https://raw.githubusercontent.com/mzStack/.github/main/assets/images/european-union-emblem.jpg" alt="European Union" width="180"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://biofair.uk/"><img src="https://raw.githubusercontent.com/mzStack/.github/main/assets/images/biofair-logo.png" alt="BioFAIR" width="160"></a>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="https://elixir-europe.org/"><img src="https://raw.githubusercontent.com/mzStack/.github/main/assets/images/elixir-logo.svg" alt="ELIXIR" width="120"></a>
</p>

## Licensing

Each mzStack repository will provide its own licensing information as it is released. Please refer to the relevant repository for the applicable terms.
