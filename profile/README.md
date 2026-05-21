# EDA Commons

Open-source infrastructure for electronic design automation.

Community-maintained, license-permissive tooling for the open-silicon
ecosystem: one engine and shared grammars handle **reading, writing,
and validating** LEF, DEF, Liberty, SPEF, Verilog netlist, GDSII, and
more — replacing the fragmented per-project implementations that
currently make tool interoperability painful.

## What this enables

- **Reading.** Drop the format-specific parsers from open-source EDA
  tools (OpenROAD, OpenLane, Yosys, KLayout, …); load files through
  one engine driven by the shared community grammar repository.

- **Writing.** Construct EDA data programmatically in memory (Python
  or C++) and emit it in any supported format — the same grammar that
  parses also serialises. **Build your own PDK**, generate cell
  libraries, produce custom netlist views, write GDSII or Liberty
  files without depending on a format-specific encoder library.
  Bidirectional from day one.

- **Schema validation before write.** Walk a constructed value tree
  against the grammar without producing output; catch missing fields,
  type errors, and structural mistakes upfront with field-level error
  paths. The grammar is the schema — no duplicate type definitions
  to maintain in sync.

- **Format evolution as a feature, not a problem.** LEF moves 5.6 →
  5.7 → 5.8. Liberty schemas drift across vendor revisions. Verilog
  adds SystemVerilog constructs. In rawast each format *version* is
  one community grammar file (`lef-5.8.rawast`, `lib-2.0.rawast`,
  …). Tools never have to "support the new version" — the grammar is
  the version. Migrations are `rawast convert` invocations between
  grammars; archives stay readable forever because each `.jast`
  container embeds the grammar that decoded it.

- **Per-grammar Python packages.** Auto-generated Pydantic models
  from any rawast grammar — `pip install rawast-lef` gives you
  `from rawast_lef import Library, Cell, Pin` with IDE autocomplete
  and runtime validation; construct, validate, and write LEF files
  from typed Python objects.

## Projects

- **[rawast](https://github.com/edacommons/rawast)** — the
  data-driven bidirectional PEG parser engine. One grammar drives
  parse, save, and validate. Production GDSII files (GF180MCU, IHP130
  layouts) parse cleanly through the data-driven grammar; round-trip
  byte-identical on tested inputs. *In private development; public
  release planned for the M4 milestone.*

## Why this organisation exists

Every open-source EDA project ships its own parsers for the formats
above. They diverge in quirks, bug-fix latency, and feature support;
format revisions take months to propagate; new tooling pays the
parser-writing tax upfront. The community-maintained alternative —
one engine, shared grammars, bidirectional from day one — is what
this organisation exists to build.

## Contact

Maintained by [Serge Rabyking](https://linkedin.com/in/serge-rabyking-b556ab89),
Marbella, Spain.
