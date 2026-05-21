# EDA Commons

Open-source infrastructure for electronic design automation.

We build community-maintained, license-permissive tooling for the
open-silicon ecosystem — file-format parsers, format converters,
schema validators, and similar infrastructure — replacing the
fragmented per-project implementations that currently make tool
interoperability painful.

## Projects

- **[rawast](https://github.com/edacommons/rawast)** — a data-driven
  predictive PEG parser engine for structured text and binary EDA
  formats. One grammar drives parse, save, and validate. Designed as
  the substrate for a community grammar repository covering LEF, DEF,
  Liberty, SPEF, Verilog netlist, GDSII, and beyond. *(In private
  development; public release planned for the M4 milestone.)*

## Why

Every open-source EDA project (OpenROAD, OpenLane, Yosys, KLayout, …)
ships its own parsers for LEF, DEF, Liberty, SPEF, Verilog netlist,
and GDSII. They diverge in quirks and bug-fix latency. Format
revisions take months to propagate. New tooling pays the
parser-writing tax upfront. The community-maintained alternative —
one engine and a shared grammar repository — is what this
organisation exists to build.

## Contact

Maintained by [Serge Rabyking](https://linkedin.com/in/serge-rabyking-b556ab89),
Marbella, Spain.
