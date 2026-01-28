# 🇮🇳 Indian Food Nutrition Database

**Free, open-source nutrition data for 620+ Indian foods**

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)
[![Foods](https://img.shields.io/badge/Foods-620-green.svg)]()
[![Categories](https://img.shields.io/badge/Categories-20-blue.svg)]()

## 📊 What's Included

Comprehensive nutrition data for **620 Indian foods** across **20 categories**:

| Category | Foods |
|----------|-------|
| Cereals & Millets | 30 |
| Grain Legumes (Dals) | 30 |
| Green Leafy Vegetables | 43 |
| Other Vegetables | 86 |
| Fruits | 83 |
| Roots & Tubers | 23 |
| Condiments & Spices | 34 |
| Nuts & Oil Seeds | 28 |
| Milk & Milk Products | 12 |
| Eggs | 15 |
| Poultry | 19 |
| Animal Meat | 73 |
| Marine Fish | 102 |
| Shellfish & Mollusks | 15 |
| Fresh Water Fish | 10 |
| Edible Oils & Fats | 4 |
| Sugars | 7 |
| Mushrooms | 4 |
| Miscellaneous | 2 |

### Nutrients Tracked (per 100g)
- Energy (kcal)
- Protein (g)
- Fat (g)
- Carbohydrates (g)
- Fiber (g)
- Calcium (mg)
- Iron (mg)
- Vitamin C (mg)

## 📥 Download Formats

### JSON (Full)
```bash
# All foods
curl -O https://raw.githubusercontent.com/prabhubng/indian-nutrition-data/main/data/foods.json

# By category
curl -O https://raw.githubusercontent.com/prabhubng/indian-nutrition-data/main/data/cereals-and-millets.json
```

### CSV
```bash
curl -O https://raw.githubusercontent.com/prabhubng/indian-nutrition-data/main/data/indian-foods.csv
```

### NPM Package
```bash
npm install indian-nutrition-data
```
```javascript
const nutrition = require('indian-nutrition-data');

// Search
const results = nutrition.search('paneer');
// [{ name: 'Paneer', energy: 265, protein: 18.3, ... }]

// Get by ID
const rice = nutrition.getById(1);

// Filter by category
const dals = nutrition.getByCategory('Grain Legumes');
```

### Python Package
```bash
pip install indian-nutrition
```
```python
from indian_nutrition import foods

# Search
results = foods.search('dal')

# Get all
all_foods = foods.all()

# Filter
veggies = foods.filter(category='Green Leafy Vegetables')
high_protein = foods.filter(protein_min=20)
```

## 🔍 Quick Examples

### JavaScript
```javascript
const foods = require('./data/foods.json').foods;

// Find high protein vegetarian foods
const highProteinVeg = foods.filter(f => 
  f.protein > 15 && 
  !['Poultry', 'Animal Meat', 'Marine Fish'].includes(f.category)
);
```

### Python
```python
import json

with open('data/foods.json') as f:
    data = json.load(f)

# Find foods with most iron
sorted_by_iron = sorted(data['foods'], key=lambda x: x['iron'], reverse=True)[:10]
```

### Google Sheets
1. Open [Google Sheets](https://sheets.google.com)
2. File → Import → Upload `indian-foods.csv`
3. Use filters and formulas!

## 📋 Data Schema

```json
{
  "id": 1,
  "name": "Rice, raw, milled",
  "nameHindi": "चावल",
  "category": "Cereals and Millets",
  "energy": 356,
  "protein": 6.8,
  "fat": 0.5,
  "carbs": 78.2,
  "fiber": 0.2,
  "calcium": 10,
  "iron": 0.7,
  "vitaminC": 0,
  "source": "IFCT 2017"
}
```

## 📚 Data Sources

This database is compiled from official Indian government nutrition research:

1. **IFCT 2017** - Indian Food Composition Tables
   - Publisher: National Institute of Nutrition (NIN), ICMR
   - Location: Hyderabad, India
   - Foods: 528 items

2. **Gopalan 2004** - Nutritive Value of Indian Foods
   - Authors: C. Gopalan, B.V. Rama Sastri, S.C. Balasubramanian
   - Publisher: NIN, ICMR
   - Supplementary foods: 92 items

## 🆓 License

**CC0 1.0 Universal (Public Domain)**

You can:
- ✅ Use commercially
- ✅ Modify and distribute
- ✅ Use without attribution
- ✅ Build apps, products, services

No permission needed. Just use it!

## 🙏 Acknowledgments

- National Institute of Nutrition (NIN), Hyderabad
- Indian Council of Medical Research (ICMR)
- All the researchers who compiled this valuable data

## 🤝 Contributing

Found an error? Want to add more foods?

1. Fork the repository
2. Edit the JSON/CSV
3. Submit a Pull Request

Please cite your source for any additions.

## 📞 Contact

- Issues: [GitHub Issues](https://github.com/user/indian-nutrition-data/issues)
- Email: [your-email]

---

**Made with ❤️ for healthier India**

*If this helps you, consider starring ⭐ the repo!*
