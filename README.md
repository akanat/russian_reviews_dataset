# Reviews Dataset

## Dataset was collected by: 
https://github.com/n1EzeR/kaspi_parser

## Dataset was compiled and partially cleaned by:
https://github.com/n1EzeR/kaspi_tazalau

## Dataset contains:
1. 112 049 Russian reviews
2. 6 756 Kazakh reviews
3. 243 undetected language reviews (numbers like "10/10", English or Kazakh in latin)

## Dataset structure:
### Review format
- Review text might be in `text` and/or in `plus` and/or in `minus`
- At least one of the columns is filled
### Category format
Number of categories: 17
- parfumes
- smartphones
- tires
- watches
- wearables
- etc.
### Rating format:
- Integers from 1 to 5
### Language format
- russian
- kazakh
- other
### Sample
| text  | plus | minus  | language | rating  | category |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| Парфюм оригинальный. Обожаю их! |  |  | russian  | 5  | parfumes  |
|  | Иісі қатты ұнады. |  | kazakh  | 5  | parfumes  |
| Телефон хороший. Все устраивает, покупкой довольна. |  |  | russian  | 5  | smartphones  |

# Cleaned Dataset 
### Differs from raw data by:
- Stopwords are removed (find them in `kaspi_tazalau/code/constants.py`)
- Tags are removed (e.g. `<br>`, `</br>`, `<p>`)
- Russian words are lemmatized (via pymystem3)
- `text`, `plus` and `minus` columns are concatenated into one `combined_text` column
