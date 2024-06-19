# recipe scaling app

potential names? LOL
-Brewbie
-Brewey

App where the primary function is for Creating, Editing, and Scaling an entire coffee recipe to make it easier to dial-in coffee, adjust ingredient ratios, or adjust the total serving size, along with additional additives like milk etc.

**Why?**
1. Dialling-in coffee is all about ratio afaik. It's really annoying having to calculate again when I want to change a small amount of an individual ingredient while keeping the other ratios.
2. Sometimes you have leftover ingredients with really awkward amounts and its a headache trying to calculate according to the right ratio.

### Creating/Editing Recipe (ratios unlocked):
Create and adjust the recipe.

Two categories of inputs:
- Ingredients (any name/unit)
- Steps/Time (wont be calculated)

	- Coffee (g)
	- Water (ml)
	- Brew Time/Step
	- Milk
	- Other Ingredients

Allow the user to add things freely.

#### Example Implementation will look like:

|                 |        |      |             |                                      |
| --------------- | ------ | ---- | ----------- | ------------------------------------ |
| Ingredient/Step | Amount | Unit | Type/Brand  | Notes                                |
| Coffee          | 20     | g    | Yirgacheffe | abit too strong, maybe lower dosage? |
| Water           | 200    | ml   |             |                                      |
| Steep           | 4      | mins |             | too sour, brew longer                |
| Milk            | 150    | ml   | Meiji       |                                      |
| Condensed Milk  | 3      | tsp. | Dawn        | WAY too sweet                        |
If there's multiple brewing steps like in pourovers, no problem since can do multiple and freeform inputs.
Key in under Ingredient/Step, fill in the Unit as Time,

**Brand/Variation:**
Lets user to store and switch the amounts of specific ingredient using its Dropdown Menu.
Like different amount of milk depending on the brand.

**E.g.**
150ml milk if Meiji
100ml milk if Farmhouse

Adding that feature universally to any ingredient will be a HUUUGE convenience.
### Scaling the Recipe (CALCULATOR MODE):

Maybe add a "default" or "reset" feature for recipes to save default/normal recipe amounts.

changing any of the values will shift the whole recipe.
brew time will remain an independent variable

## Extra Features?

- Ability to add pictures to the recipes and ingredients.
- Sharing to social media apps?
- Cloud syncing based on accounts?
	- Or if I take Obsidian's idea and use Markdown to store data?

## The programming?

If it's programmed by relative ratios, a "base" reference is probably needed.
For coffee it's obviously the coffee grounds, because the dosage and whatnot are all surrounding the coffee.

Pseudocodes with Example Scenarios:

Creating a Recipe:
```
User to input ingredient amounts:

Base/Reference Ingredient, B
Ingredient 1, ingre1
Ingredient 2, ingre2

Calculate the Ratios of ingredients:
ingre1 / B
ingre2 / B

Store the data
```

Editing a Recipe:

```
User Inputs/Edits a new ingredient amount:
Ingredient 2, ingre2

Calculate the Ratios of ingredients:
ingre2 / B

Store the data
```

Scaling a Recipe (Calculator Mode):

```
User inputs an altered amount for Ingredient 2:
Ingredient 2, ingre2

Calculate the Relative Change of amount:
change = new ingre2 / old ingre2

Calculating the other ingredients:
New B = Old B * change
New ingre1 = Old ingre1 * change
```
