# MIXOLATOR

A single-file, offline recipe calculator for the wet lab with password protection. It turns a library of stock
solutions into a ready-to-pipette recipe, shows the volume of every component, flags the
ones that need attention, and exports a formatted spreadsheet with the calculations kept
as live formulas.

The whole tool is one HTML file. It runs in any modern browser with no server, no install
and no internet connection, so it works on a lab computer, a laptop or a tablet.

## What it does

You keep your own library of stocks once, then build recipes from it. For every recipe the
tool works out how much of each component to pipette, how much buffer to add and how much
water fills the rest, and warns when a volume is too small to pipette accurately or when the
numbers do not add up.

It handles three kinds of preparation, each with its own step-by-step workflow:

- **Aqueous mixes** — components combined by final concentration and topped up with water
  or a buffer. Supports stock predilutions, components counted in different units, premixes
  that are made first and go in as one ingredient, components whose concentration follows
  another, and a labelled/unlabelled split.
- **Lipid mixes** — lipids combined by mol%, either taken up in solvent as a stock or dried
  and resuspended in an oil blend mixed by volume.
- **Stock buffers** — made from solids and solutions, with the weigh / dissolve / adjust /
  fill / filter / store steps generated automatically and scaled to any final volume.

A built-in calculator converts an absorbance reading (for example from a spectrophotometer)
into a concentration using the extinction coefficient, with an optional dye correction and a
mass/molar converter.

## Unit handling

Concentrations can be entered in molar or mass units and are converted using the molecular
weight where needed. Volumes, amounts and dilution factors are shown in sensible units and
the conversions are visible, so every number can be traced back to its inputs.

## Output

- **Excel export** — a formatted spreadsheet that fits one page for printing. The cells
  contain the actual formulas, not just the final numbers, so the calculation can be followed
  and adjusted after the file is saved.
- **Copy to clipboard** — a plain-text version of the recipe for a notebook or a message.
- **Reload** — an exported spreadsheet can be loaded back into the tool to continue editing.

## Your data

The library and your work-in-progress recipes are stored in your own browser. The tool can
also save everything back into the HTML file itself, so the file becomes a portable, shareable
copy that carries your library with it. The library can additionally be exported and
re-imported as a spreadsheet or a small data file for backup or sharing.

Nothing is ever sent anywhere. All calculation and storage happen locally in the browser.

## Extensibility

Everything in the library is editable in the tool, with no code changes: add or change
ingredients (with their stock concentration, units, molecular weight and other properties),
group ingredients into packages that are added together, define premixes, and save complete
recipes as reusable starting points.

## Using it

Open the HTML file in a browser. On a tablet, add it to the home screen to open it like an app.

### Hosting it privately

If you want to reach it from several devices, the file can be put on any static host. Because
a plain web page has no login, do not upload the file as-is if its contents are private.
Instead, encrypt the single HTML file with a password first (for example with a static-site
encryption tool) and upload only the encrypted version; it is then decrypted in the browser
after the password is entered. Choose a long, unusual password, as an encrypted file can be
copied and guessed against offline.
