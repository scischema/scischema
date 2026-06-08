# Contributing to SciSchema

Thank you for contributing to SciSchema.

SciSchema is a community-driven collection of machine-readable scientific process schemas. Contributions are welcome through GitHub pull requests.

## Adding a New SciSchema Schema

### 1. Fork the Repository

Fork:

```
https://github.com/scischema/scischema
```

Then create a new branch, for example:

```
add-pcr-schema
```

---

### 2. Add the Schema JSON

Place the new JSON Schema file in:

```
auto-gen/schema-json/
```

Example:

```
auto-gen/schema-json/pcr.json
```

---

### 3. Add One Metadata Row

Edit:

```
auto-gen/schema-metadata.csv
```

Add one row with the schema metadata, including:

```
filename, process_name, domain_slug, domain_name, slug, description, orkg_url
```

Example:

```csv
pcr.json,PCR,biology,Biology,pcr,Polymerase Chain Reaction is a laboratory process for amplifying DNA.,https://orkg.org/...
```

---

### 4. Run the Generator

From the repository root, run:

```bash
python auto-gen/generate_schema_pages.py
```

This creates:

```
schemas/<domain_slug>/<slug>/index.html
schemas/<domain_slug>/<slug>/master-schema.json
```

Example:

```
schemas/biology/pcr/index.html
schemas/biology/pcr/master-schema.json
```

---

### 5. Check the Generated Page

Open the generated `index.html` locally or inspect it in GitHub.

Confirm that:

* the title is correct;
* the description is correct;
* the properties table is populated;
* the `master-schema.json` download link works;
* the ORKG link is correct, if provided.

---

### 6. Commit the Changes

Commit:

```
auto-gen/schema-json/<schema>.json
auto-gen/schema-metadata.csv
schemas/<domain_slug>/<slug>/index.html
schemas/<domain_slug>/<slug>/master-schema.json
```

---

### 7. Open a Pull Request

The pull request should include:

* the schema JSON;
* the metadata CSV update;
* the generated schema page;
* the generated `master-schema.json`.

---

### 8. Review Criteria

A schema contribution can be merged when:

* the JSON file is valid;
* the metadata row is complete;
* the schema has a clear scientific-process scope;
* the generated page renders correctly;
* the folder path follows:

```
schemas/<domain_slug>/<slug>/
```

* the schema file is named:

```
master-schema.json
```

in the final schema folder.

## Recommended Pull Request Template

```markdown
## New SciSchema Schema

### Schema Information

Schema name:

Domain:

Slug:

Short description:

ORKG template URL (if available):

Contributor Github username (@username):

### Files Added or Updated

- [ ] Added JSON Schema file to `auto-gen/schema-json/`
- [ ] Added metadata row to `auto-gen/schema-metadata.csv`
- [ ] Ran `python auto-gen/generate_schema_pages.py`
- [ ] Generated `schemas/<domain_slug>/<slug>/index.html`
- [ ] Generated `schemas/<domain_slug>/<slug>/master-schema.json`

### Checks

- [ ] JSON file is valid
- [ ] Metadata row is complete
- [ ] Generated page displays correctly
- [ ] Download link to `master-schema.json` works
- [ ] ORKG link works, if provided
```

