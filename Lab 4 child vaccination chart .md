# lab 4: child vacation chart 

``` python 

patients = {}

def insert (record_number, First_name, Last_name, Vac_month):
  patients[record_number] = {
    "First_name": First_name,
    "Last_name": Last_name,
    "Vac_month": Vac_month
}

def main():
# John Smith's vac schedule 

  vaccines1 = {
      "HepB": [0, 1, 6],
      "RV": [2, 4, 6],
      "DRaP": [2, 4, 6, 15],
      "Hib": [2, 4, 6, 15],
      "PCV13": [2, 4, 6, 12],
      "IPV": [2, 4, 6],
      "IIV4": ["Annual"],
      "MMR": [12],
      "VAR": [12],
      "HepA": [12]
  }

# insert John's into the patients dictionary

  insert("R001", "John","Smith", vaccines1)

  print("\nPatient records after first insert:")
  print(patients)

# Olivia James's vac schedule

  vaccines2 = {
      "HepB": [0, 1, 6],
      "RV": [2, 4, 7],
      "DRaP": [2, 5, 7, 12],
      "Hib": [2, 4, 6, 12],
      "PCV13": [2, 5, 7, 12],
      "IPV": [2, 5, 8],
      "IIV4": ["Annual"],
      "MMR": [12],
      "VAR": [12],
      "HepA": [12]
  }

# insert Olivia's into the patient's dictionary

  insert("R002", "Olivia", "James", vaccines2)

  print("\nPatient records after adding second patient:")
  print(patients)

if __namee__ == "__main__":
  main()

```

# video 
https://drive.google.com/file/d/1lAm9iLtuEb7hSxdbv9Wyoop1BPt_Tg86/view?usp=sharing 
