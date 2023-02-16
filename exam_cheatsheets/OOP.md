# OOP (Object oriented programming)
##### Unterstützt durch ChatGPT, verfasst und geprüft von [fabischw](https://github.com/fabischw)


# Begriffe:

- Klassen: "Bauplan" eines Objekts
- Instanzen: "lebendige" Objekte nach dem Bauplan einer Klasse erstellt
- Objekte: Begriff wird unterschiedlich verwendet
- Methoden: Prozeduren und Funktionen, die Teil einer Klasse sind
- Attribute oder Felder: 'Variablen' , die zu einem Objekt gehören und damit seinen Zustand beschreiben
- Eigenschaften oder Properties: regeln Lese- und Schreibzugriffe auf Attribute

### Beispiel in python:

```python
# Definition einer Klasse namens "Person"
class Person:
    # Konstruktor-Methode, die bei der Instanziierung der Klasse aufgerufen wird
    def __init__(self, name, alter):
        # Attribute oder Felder, die zu einem Objekt gehören und seinen Zustand beschreiben
        self.name = name
        self.alter = alter

    # Methode, die Teil der Klasse ist und eine Eigenschaft zurückgibt
    def is_volljaehrig(self):
        return self.alter >= 18

# Instanziierung zweier Objekte der Klasse "Person"
person1 = Person("Max", 25)
person2 = Person("Anna", 17)

# Aufruf der Methode "is_volljaehrig" für jedes Objekt
print(person1.is_volljaehrig())  # gibt True zurück
print(person2.is_volljaehrig())  # gibt False zurück

# Änderung eines Attributs durch eine Eigenschaft
person1.name = "Maximilian"
print(person1.name)  # gibt "Maximilian" zurück


```

<details>
<summary>Erklärung</summary>

In diesem Beispiel ist Person eine Klasse, die als "Bauplan" für Objekte dient, die eine Person repräsentieren. Wenn wir ein neues Objekt erstellen, wird es als "Instanz" der Klasse bezeichnet, da es auf dem Bauplan basiert. Die Attribute name und alter sind "Felder" oder "Variablen", die zum Objekt gehören und seinen Zustand beschreiben.

Die Methode is_volljaehrig ist Teil der Klasse und gibt eine "Eigenschaft" zurück, die den Lesezugriff auf das Attribut alter regelt. Das bedeutet, dass wir den Wert von alter nicht direkt ändern können, sondern nur über die Methode is_volljaehrig darauf zugreifen können.

Schließlich zeigt das Beispiel, wie man das Attribut name durch eine Eigenschaft ändern kann, die den Schreibzugriff regelt. person1.name = "Maximilian" ruft den "Setter" der Eigenschaft auf und ändert den Wert des Attributs name auf "Maximilian".

</details>




# weitere Begriffe (getter, setter, public vs private attributes)

- Getter-Methode: Methode, die den Wert eines privaten Attributs zurückgibt.
- Setter-Methode: Methode, die den Wert eines privaten Attributs ändert.
- Public Attribute: Attribute, auf die von außerhalb der Klasse direkt zugegriffen werden kann.
- Private Attribute: Attribute, auf die von außerhalb der Klasse nicht direkt zugegriffen werden kann.

### Beispiel in python:



```python
class Person:
    def __init__(self, name, alter):
        self._name = name  # Private Attribut
        self.alter = alter  # Public Attribut

    def is_volljaehrig(self):
        return self.alter >= 18

    # Getter-Methode für das private Attribut "_name"
    def get_name(self):
        return self._name

    # Setter-Methode für das private Attribut "_name"
    def set_name(self, name):
        self._name = name

    # Getter-Methode für das public Attribut "alter"
    def get_alter(self):
        return self.alter

    # Setter-Methode für das public Attribut "alter"
    def set_alter(self, alter):
        self.alter = alter


person1 = Person("Max", 25)
person2 = Person("Anna", 17)

print(person1.get_name())  # gibt "Max" zurück
person1.set_name("Maximilian")
print(person1.get_name())  # gibt "Maximilian" zurück

print(person1.get_alter())  # gibt 25 zurück
person1.set_alter(30)
print(person1.get_alter())  # gibt 30 zurück

```

<details>
<summary>Erklärung</summary>

In diesem Beispiel wurde das private Attribut _name hinzugefügt, das nur innerhalb der Klasse zugänglich ist. Das public Attribut alter bleibt unverändert.

Um auf das private Attribut _name zuzugreifen, wurden Getter- und Setter-Methoden hinzugefügt. Die Getter-Methode get_name gibt den Wert des privaten Attributs zurück, während die Setter-Methode set_name den Wert des privaten Attributs ändert.

Ebenso wurden Getter- und Setter-Methoden für das public Attribut alter hinzugefügt. Diese Methoden ermöglichen es, den Zugriff auf die Attribute der Klasse zu regeln, anstatt sie direkt zu ändern.

Wenn man nun person1.get_name() aufruft, gibt die Getter-Methode den Wert von _name zurück, der zuvor auf "Maximilian" geändert wurde. Wenn man person1.set_alter(30) aufruft, wird das Alter des Objekts auf 30 gesetzt, da die Setter-Methode set_alter auf das public Attribut alter zugreift.

</details>


