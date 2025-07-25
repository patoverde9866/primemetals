```mermaid
classDiagram
    class ContactsPage {
        -searchTerm: string
        -typeFilter: ContactType | ""
        -showSettings: boolean
        -refreshKey: number
        +handleDelete(id: string): void
        +getContacts(search: string, type: ContactType | undefined): Contact[]
    }

    class ContactTable {
        +contacts: Contact[]
        +onDelete(id: string): void
    }

    class GearIcon {
        +onClick(): void
    }

    class SettingsModal {
        +isOpen: boolean
        +onClose(): void
        +module: string
        +onUpdate(): void
    }

    class ContactType {
        <<Enumeration>>
        customer
        vendor
    }

    ContactsPage --> ContactTable : uses
    ContactsPage --> GearIcon : uses
    ContactsPage --> SettingsModal : uses
    ContactsPage --> ContactType : uses