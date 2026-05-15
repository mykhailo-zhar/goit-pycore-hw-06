# goit-pycore-hw-06: Address Book

Implement a simple **address book** in Python using classes and inheritance. Contacts are stored as **records** (name plus phone numbers) inside an **address book** container.

## Domain model

| Class | Role |
| --- | --- |
| `Field` | Base type for a single stored value with `validate()` |
| `Name` | Contact name (required, non-empty string) |
| `Phone` | Phone number (exactly 10 digits) |
| `Record` | One contact: a `Name` and a list of `Phone` instances |
| `AddressBook` | Collection of `Record` objects keyed by contact name |

See the [class diagram](docs/source/class-diagram.rst) for relationships between types.

## What to implement

Code lives under `src/`:

- **`src/fields/`** — `Field`, `Name`, and `Phone` with validation in `validate()`.
- **`src/record.py`** — create a record, add/remove/edit/find phones, and format `__str__` output.
- **`src/address_book.py`** — add, find, and remove records by name.

`main.py` shows example usage: create records, add them to the book, edit a phone, and remove a contact.

## Validation and errors

- A record must have a valid **name**; otherwise raise `ValueError`.
- Phone numbers must match `^\d{10}$`; invalid numbers raise `ValueError` on add or edit.
- Do not add duplicate phones to the same record.
- Editing or removing a phone that does not exist should fail or return `False` as specified in the tests.

## Verify your work

```bash
mise trust && mise install
uv sync
mise run test
```

Tests are in `tests/`. Optional: `mise run lint` and `python main.py`.
