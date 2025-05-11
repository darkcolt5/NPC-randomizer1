# NPC-randomizer1
import sys
import random
import pandas as pd


def get_name(race, gender, region):

  if race == "Humans" and gender == "Male" and region == "Borealans":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=(f"{region} {race}"))
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, 20), 4]
    return f"{firstName} {lastName}"

  elif race == "Humans" and gender == "Female" and region == "Borealans":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=(f"{region} {race}"))
    firstName = df.iloc[random.randint(1, len(df) - 1), 2]
    lastName = df.iloc[random.randint(1, 20), 4]
    return f"{firstName} {lastName}"

  elif race == "Humans" and gender == "Male" and region == "Tropicanis":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=(f"{region} {race}"))
    firstName = df.iloc[random.randint(1, 19), 0]
    lastName = df.iloc[random.randint(1, 19), 4]
    return f"{firstName} {lastName}"

  elif race == "Humans" and gender == "Female" and region == "Tropicanis":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=(f"{region} {race}"))
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, 19), 4]
    return f"{firstName} {lastName}"

  elif race == "Humans" and gender == "Male" and region == "Selvarossa":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=(f"{region} {race}"))
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, len(df) - 1), 4]
    return f"{firstName} {lastName}"

  elif race == "Humans" and gender == "Female" and region == "Selvarossa":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=(f"{region} {race}"))
    firstName = df.iloc[random.randint(1, len(df) - 1), 2]
    lastName = df.iloc[random.randint(1, len(df) - 1), 4]
    return f"{firstName} {lastName}"

  elif race == "Orcs":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, len(df) - 1), 2]
    return f"{firstName} {lastName}"

  elif race == "Dwarves":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, len(df) - 1), 2]
    return f"{firstName} {lastName}"

  elif race == "Aelves" and gender == "Male":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, 10), 0]
    lastName = df.iloc[random.randint(1, len(df) - 1), 4]
    return f"{firstName} {lastName}"

  elif race == "Aelves" and gender == "Female":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, 10), 2]
    lastName = df.iloc[random.randint(1, len(df) - 1), 4]
    return f"{firstName} {lastName}"

  elif race == "Centaurs" and gender == "Male":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    return f"{firstName}"

  elif race == "Centaurs" and gender == "Female":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 2]
    return f"{firstName}"

  elif race == "Saurians":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, 12), 2]
    return f"{firstName} {lastName}"

  elif race == "Faeries":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, len(df) - 1), 2]
    return f"{firstName} {lastName}"

  elif race == "Halflings" and gender == "Male":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 0]
    lastName = df.iloc[random.randint(1, len(df) - 1), 4]
    return f"{firstName} {lastName}"

  elif race == "Halflings" and gender == "Female":
    df = pd.read_excel("Npc Names.xlsx", sheet_name=race)
    firstName = df.iloc[random.randint(1, len(df) - 1), 2]
    lastName = df.iloc[random.randint(1, len(df) - 1), 4]
    return f"{firstName} {lastName}"
  else:
    return "Peter griffen"


def HeightCal(min, max):
    heightCM = random.randint(int(min), int(max))
    inches = heightCM * 0.393701
    feet = int(inches // 12)
    inches = int(inches % 12)
    return f"{feet}'{inches}\""

class Npc:  # NPC class
    def __init__(self):
      self.region = random.choice(["Borealans","Tropicanis","Selvarossa","Verdanian"])
      self.Gender = random.choice(["Male", "Female"])

      if self.region == "Borealans":
        self.race = random.choice(["Humans", "Orcs", "Dwarves" ])
        self.city = random.choice(["Hinterborne", "Frostmoor", "Drakkenstone"])

      elif self.region == "Tropicanis":
        self.race = random.choice(["Humans", "Saurians", "Halflings"])
        self.city = random.choice(["Everspring", "Doradel", "Calthos", "Langrisha", "Hambshala", "Lavayon"])

      elif self.region == "Selvarossa":
        self.race = random.choice(["Humans", "Aelves", "Faeries"])
        self.city = random.choice(["Bellariva", "Castrovivo", "Vetricella", "Castanera", "Rovella", "Forcillia"])

      elif self.region == "Verdanian":
        self.race = random.choice(["Centaurs", "Dwarves", "Aelves", "Orcs"])
        self.city = random.choice(["Thistleton", "Skylorne", "Thornfell", "Redhook"])

      if self.race == "Humans":
        self.eye_color = random.choice(["Blue", "Brown", "Green", "Hazel", "Amber"])
        self.hair_color = random.choice(["Black", "Brown", "Red", "Blonde", "Gray"])
        self.weight = random.randint(80, 400)
        self.height = HeightCal(147.32, 198.12)

      elif self.race == "Orcs":
        self.eye_color = random.choice(["Black", "Brown", "Red"])
        self.hair_color = random.choice(["Black",])
        self.weight = random.randint(250, 600)
        self.height = HeightCal(177.8, 228.6)

      elif self.race == "Dwarves":
        self.eye_color = random.choice(["Black", "Brown"])
        self.hair_color = random.choice(["Black", "Brown", "Red", "Blonde", "Gray"])
        self.weight = random.randint(200, 400)
        self.height = HeightCal(121.92, 165.1)

      elif self.race == "Saurians":
        self.eye_color = random.choice(["Purple", "Red", "Black"])
        self.hair_color = random.choice(["N/A"])
        self.weight = random.randint(150, 300)
        self.height = HeightCal(137.16, 182.88)

      elif self.race == "Halflings":
        self.eye_color = random.choice(["Blue", "Brown", "Green", "Hazel", "Amber"])
        self.hair_color = random.choice(["Black", "Brown", "Red", "Blonde", "Gray"])
        self.weight = random.randint(40, 150)
        self.height = HeightCal(106.68, 147.32)

      elif self.race == "Aelves":
        self.eye_color = random.choice(["Blue", "Brown", "Green", "Hazel", "Amber", "Lilac", "Red"])
        self.hair_color = random.choice(["Blonde", "White", "Silver", "Copper", "Black"])
        self.weight = random.randint(120, 200)
        self.height = HeightCal(170.18, 208.28)

      elif self.race == "Faeries":
        self.eye_color = random.choice(["Gold", "Red", "Green", "Blue", "Magenta"])
        self.hair_color = random.choice(["Black", "Brown", "Red", "Orange", "Yellow", "Green", "Blue", "Purple"])
        self.weight = random.randint(30, 100)
        self.height = HeightCal(91.44, 137.16)

      elif self.race == "Centaurs":
        self.eye_color = random.choice(["Blue", "Brown", "Green", "Hazel", "Amber"])
        self.hair_color = random.choice(["Brown", "White", "Black", "Gray", "Auburn"])
        self.weight = random.randint(1000, 2500)
        self.height = HeightCal(182.88, 274.32)

      #Strength
      lowest = 999
      total = 0
      for _ in range(4):
        num = random.randint(1, 6)
        if num < lowest:
          lowest = num
        total += num    
      self.strength = total - lowest

      #Logic
      total = 0
      for _ in range(3):
        num = random.randint(1, 6)
        while num == 1:
          num = random.randint(1, 6)  
        total += num    
      self.logic = total

      #Agility
      Highest = -999
      total = 0
      for _ in range(5):
        num = random.randint(1, 6)
        if num > Highest:
          Highest = num
        total += num 
      total -= Highest
      if total > 18:
        total = 18
      self.agility = total

      #Intellect
      total = 0
      for _ in range(2):
        num = random.randint(1, 6)
        total += num
      total += 6
      self.intellect = total

      #Toughness
      total = 0
      lowest = 999
      for _ in range(4):
        num = random.randint(1, 6)
        while num == 1:
          num = random.randint(1, 6)
        if num < lowest:
          lowest = num  
        total += num    
      self.toughness = total - lowest

      #Charisma
      num = random.randint(1, 20)
      if num == 1:
        num += 2
      if num > 10:
        num -= 2
      self.charisma = num

      self.name = get_name(self.race, self.Gender, self.region)

    def describe(self):
        print(f"Name: {self.name}")
        print(f"Region: {self.region}")
        print(f"City: {self.city} \n")
        print("Characteristics:")
        print(f"  Race: {self.race}")
        print(f"  Gender: {self.Gender}")
        print(f"  Eye Color: {self.eye_color}")
        print(f"  Hair Color: {self.hair_color}")
        print(f"  Weight: {self.weight}")
        print(f"  Height: {self.height} \n")
        print("Character Stats:")
        print(f"  Strength: {self.strength}")
        print(f"  Logic: {self.logic}")
        print(f"  Agility: {self.agility}")
        print(f"  Intellect: {self.intellect}")
        print(f"  Toughness: {self.toughness}")
        print(f"  Charisma: {self.charisma} \n")

if __name__ == "__main__":
  while True:
    RandomNpc = Npc()
    RandomNpc.describe()
    choice = input("Do you want to generate another NPC? (yes/no): ")
    while choice.lower() not in ["yes", "no", "y", "n"]:
      choice = input("Please enter 'yes' or 'no': ")
    if choice.lower() in ["no","n"]:
      exit()
    print("\n")
