# 📑 Оглавление для навигации

## 🔹 Генеративные и дискриминативные модели
[[#1. В чём разница между генеративными (MultinomialNB) и дискриминативными (LR, LinearSVC) моделями?|1. NB vs LR/SVC]]

## 🔹 Масштабирование и расстояния
[[#2. Почему KNN чувствителен к масштабу? StandardScaler vs MinMaxScaler при выбросах|2. KNN и скалеры]]

## 🔹 Bias-Variance Tradeoff
[[#3. Как проявляется Bias-Variance Tradeoff в CatBoost (DGA) и LightGBM (HTTP Malware)?|3. Bias-Variance в бустинге]]

## 🔹 MLE и функции потерь
[[#4. Что такое MLE и как он связан с LogLoss/CrossEntropy? Почему именно она в LR и Softmax?|4. MLE → CrossEntropy]]

## 🔹 Регуляризация в тексте
[[#5. Как работают L1/L2 регуляризация в тексте? Влияние `C` и `class_weight` на веса после TF-IDF|5. L1/L2 в текстовых задачах]]

---

## 🛠️ Feature Engineering & Работа с данными

[[#6. `Family_Survival` в Titanic: это data leakage? Как правильно валидировать?|6. Family_Survival leakage]]
[[#7. Энтропия Шеннона и χ²-тест в DGA. Почему они информативнее длины строки?|7. Энтропия и χ² в DGA]]
[[#8. Почему `word` + `char_wb` n-grams в Bind/Shell & HTTP Malware?|8. Word + Char n-grams]]
[[#9. Как бороться с разреженностью после TF-IDF?|9. Разреженность TF-IDF]]
[[#10. Нормализация пакетов в `Who's Talking`: `/1500.0` + split на size/direction. Зачем?|10. Нормализация трафика]]

---

## 🧠 Модели & Алгоритмы

[[#11. Как работает 1D-CNN в `Who's Talking`? Почему свёртки эффективнее Dense/RNN?|11. 1D-CNN для трафика]]
[[#12. Что такое `Ordered Boosting` в CatBoost и как он снижает переобучение?|12. Ordered Boosting CatBoost]]
[[#13. Математическое отличие LinearSVC от Logistic Regression. Когда они совпадают, а когда SVM лучше?|13. LinearSVC vs LR]]
[[#14. Почему LightGBM использует `leaf-wise` рост? Почему нужен жёсткий контроль?|14. Leaf-wise в LightGBM]]
[[#15. Как работает Batch Normalization? Зачем он после каждого Conv1D?|15. BatchNorm в CNN]]

---

## 📊 Валидация, Метрики & Пороговая оптимизация

[[#16. Почему в `DGA` ты оптимизировал Fβ=0.5, а в `Bind/Shell` и `HTTP Malware` — F1? Приоритет Precision vs Recall в Security|16. Fβ в Security]]
[[#17. Как работает Out-of-Fold (OOF) валидация? Почему надёжнее `train_test_split` для порога?|17. OOF валидация]]
[[#18. Калибровка вероятностей (Platt, Isotonic). Зачем перед усреднением LR + LGBM?|18. Калибровка вероятностей]]
[[#19. Почему Accuracy бессмыслен при дисбалансе, а PR-AUC информативнее ROC-AUC? Пример `Bind/Shell`|19. PR-AUC vs ROC-AUC]]
[[#20. Как оценивать модель при сдвиге распределения? (Covariate shift, Prior shift)|20. Сдвиг распределения]]

---

## 🤝 Ансамбли & Комбинирование моделей

[[#21. В чём разница между Voting, Stacking и Blending? Что реализовал ты?|21. Voting/Stacking/Blending]]
[[#22. Почему усреднение вероятностей (soft) стабильнее hard voting? Влияние корреляции ошибок|22. Soft vs Hard Voting]]
[[#23. Почему LR + LGBM дают синергию? Какие паттерны ловит каждая?|23. Синергия LR + LGBM]]
[[#24. Что такое Stacked Generalization? Как избежать leakage при обучении мета-модели?|24. Stacking без leakage]]
[[#25. Как выбрать веса для взвешенного энсембля? Можно ли оптимизировать автоматически?|25. Веса ансамбля]]

---

## ⚡ Оптимизация, Память & Инференс

[[#26. `float16` и `chunked inference` в `Who's Talking`. Влияние на точность/градиенты? Подводные камни смешанной точности?|26. float16 и chunking]]
[[#27. Почему в `Bind/Shell` матрицы приводились к `float32` перед `csr_matrix`? Что будет с `float64`?|27. float32 vs float64]]
[[#28. Как работают `Early Stopping` и `ReduceLROnPlateau`? Как подбирать `patience`?|28. EarlyStopping + LR]]
[[#29. Способы ускорения инференса TF-IDF + классификатор в продакшене|29. Ускорение инференса]]
[[#30. Как `gc.collect()` и `tf.keras.backend.clear_session()` влияют на память? Почему критичны в OOF-циклах?|30. Управление памятью]]

---

## 🛡️ Специфика Кибербезопасности & Domain-Specific ML

[[#31. Иерархическая логика: «1 транзакция = malware → файл = malware». Искажение метрик и правильная валидация|31. Мил-логика валидации]]
[[#32. Почему в Security часто `β<1`, а в Медицине `β>1`? Влияние стоимости FP/FN|32. β в Security vs Medicine]]
[[#33. Как бороться с Concept Drift в кибербезопасности?|33. Concept Drift в Security]]
[[#34. Опасность TF-IDF для обфусцированных/зашифрованных нагрузок + альтернативы|34. TF-IDF и обфускация]]
[[#35. Мониторинг модели после деплоя в SOC/SIEM. Метрики и реакция на деградацию|35. Мониторинг в продакшене]]

---

# 🔹 Генеративные и дискриминативные модели

## 1. В чём разница между генеративными (MultinomialNB) и дискриминативными (LR, LinearSVC) моделями?

**Кратко:** Генеративные учат `P(X|Y)·P(Y)` и выводят `P(Y|X)` через Байеса; дискриминативные учат границу решений напрямую, аппроксимируя `P(Y|X)`.

**Подробно:**
- 🔹 **MultinomialNB** делает сильное предположение: признаки независимы при условии класса. Параметризуется всего `2×V` весами (где `V` — размер словаря).
- 🔹 **LogisticRegression / LinearSVC** не требуют независимости признаков, фокусируются на разделении классов через минимизацию функции потерь.

**DevOps-контекст:** На малых выборках с разреженными текстовыми признаками (Bind/Shell: ~2% malware) NB менее склонен к переобучению благодаря сильному регуляризирующему эффекту независимости. LR/SVC дают более точную границу, но требуют больше данных и аккуратной настройки `C`, `class_weight`.

**Команды:**
```python
# NB — быстрый baseline
from sklearn.naive_bayes import MultinomialNB
clf = MultinomialNB(alpha=0.1)

# LR — с регуляризацией
from sklearn.linear_model import LogisticRegression
clf = LogisticRegression(C=0.5, class_weight='balanced', solver='lbfgs')

# LinearSVC — для больших разреженных матриц
from sklearn.svm import LinearSVC
clf = LinearSVC(C=0.5, class_weight='balanced', max_iter=3000)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🔹 Масштабирование и расстояния

## 2. Почему KNN чувствителен к масштабу? StandardScaler vs MinMaxScaler при выбросах

**Кратко:** KNN основан на метрике расстояния (обычно Евклидовой). Если признаки имеют разный масштаб, доминирующий признак искажает расстояния.

**Подробно:**
- `StandardScaler`: `z = (x - μ) / σ` — центрирует и нормирует дисперсию.
- `MinMaxScaler`: `x' = (x - min) / (max - min)` — сжимает в `[0, 1]`.

**Проблема выбросов в `Fare`:** В Titanic `Fare` имеет тяжёлый правый хвост (£500+). У `MinMaxScaler` один выброс растянет диапазон, и 95% значений сожмутся в `[0, 0.1]` — расстояния потеряют дискриминационную силу. `StandardScaler` устойчивее, но идеален пайплайн: `np.log1p(Fare)` → `StandardScaler` или `RobustScaler`.

**DevOps-контекст:** В пайплайнах пре-процессинга всегда логируйте распределение признаков перед масштабированием. Для признаков с тяжёлыми хвостами (`Fare`, `duration`, `bytes`) используйте лог-трансформацию или `QuantileTransformer`.

**Команды:**
```python
from sklearn.preprocessing import StandardScaler, RobustScaler
import numpy as np

# Лог-трансформация + StandardScaler
X['Fare_log'] = np.log1p(X['Fare'])
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X[['Fare_log', 'Age', ...]])

# Или RobustScaler для устойчивости к выбросам
robust = RobustScaler()
X_robust = robust.fit_transform(X[['Fare', 'Age', ...]])
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🔹 Bias-Variance Tradeoff

## 3. Как проявляется Bias-Variance Tradeoff в CatBoost (DGA) и LightGBM (HTTP Malware)?

**Кратко:** `Error = Bias² + Variance + Noise`. Глубина дерева и learning rate — рычаги управления балансом.

**Подробно:**
- 🔹 **High Bias** (недообучение): модель слишком простая, не улавливает паттерны. Лечится увеличением `depth`, уменьшением `min_data_in_leaf`.
- 🔹 **High Variance** (переобучение): модель «запоминает» шум. Лечится уменьшением `depth`, `learning_rate`, добавлением `early_stopping`.

**В CatBoost (DGA):** `depth=6` + `lr=0.1` + `early_stopping=150` балансируют: низкий LR снижает дисперсию каждого шага, early stopping обрезает рост при плато валидации.

**В LightGBM (HTTP Malware):** `leaf-wise` рост быстро снижает bias, но без `max_depth=10`, `num_leaves=50` деревья захватывают шум → высокий variance. Снижение LR до `0.03` сместило баланс к стабильности.

**DevOps-контекст:** В CI/CD для ML настройка гиперпараметров должна быть автоматизирована (Optuna, Hyperopt) с валидацией на временных сплитах, а не случайных, чтобы учитывать временной дрейф.

**Команды:**
```python
# CatBoost: баланс через early stopping
from catboost import CatBoostClassifier
model = CatBoostClassifier(
    iterations=1500, learning_rate=0.1, depth=6,
    early_stopping_rounds=150, use_best_model=True
)

# LightGBM: контроль leaf-wise
import lightgbm as lgb
model = lgb.LGBMClassifier(
    n_estimators=500, learning_rate=0.03,
    max_depth=10, num_leaves=50, min_data_in_leaf=50
)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🔹 MLE и функции потерь

## 4. Что такое MLE и как он связан с LogLoss/CrossEntropy? Почему именно она в LR и Softmax?

**Кратко:** MLE ищет параметры, максимизирующие вероятность данных. Логарифмирование превращает произведение в сумму — это и есть CrossEntropy.

**Подробно:**
- **Maximum Likelihood Estimation:** `θ_MLE = argmax ∏ P(y_i | x_i, θ)`
- **Логарифм правдоподобия:** `L(θ) = ∑ log P(y_i | x_i, θ)`
- Для бинарной классификации это превращается в **Binary CrossEntropy**: `−∑ [y·log(ŷ) + (1−y)·log(1−ŷ)]`

**Почему именно она:**
1. Минимизация NLL = максимизация правдоподобия (статистически оптимально)
2. Градиент получается простым: `∇ = ŷ − y` → стабильная сходимость
3. Прямо оптимизирует калиброванность вероятностей → критично для пороговой оптимизации

**DevOps-контекст:** В продакшене калиброванные вероятности позволяют гибко менять порог под бизнес-метрику без переобучения модели. Всегда логируйте `predict_proba`, а не только `predict`.

**Команды:**
```python
# LR с лог-потерей (по умолчанию)
from sklearn.linear_model import LogisticRegression
clf = LogisticRegression(loss='log_loss')  # sklearn >=1.2

# Калибровка после обучения
from sklearn.calibration import CalibratedClassifierCV
clf_calibrated = CalibratedClassifierCV(clf, method='sigmoid', cv=5)

# Проверка калибровки
from sklearn.calibration import calibration_curve
prob_true, prob_pred = calibration_curve(y_true, y_proba, n_bins=10)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🔹 Регуляризация в тексте

## 5. Как работают L1/L2 регуляризация в тексте? Влияние `C` и `class_weight` на веса после TF-IDF

**Кратко:** `L1` обнуляет слабые веса (авто-отбор признаков), `L2` плавно сжимает все. `C = 1/λ`: меньше `C` → сильнее регуляризация.

**Подробно:**
|Параметр|Эффект|Когда использовать|
|--------|--------|-----------------|
|`penalty='l1'`|Обнуляет нерелевантные n-grams|Тысячи признаков, нужен feature selection|
|`penalty='l2'`|Сжимает все веса равномерно|Коррелированные признаки, стабильность|
|`C=0.1`|Сильная регуляризация|Мало данных, риск переобучения|
|`C=10`|Слабая регуляризация|Много данных, нужна гибкость|
|`class_weight='balanced'`|Взвешивает потерю по классам|Дисбаланс > 1:10|

**`class_weight` в контексте TF-IDF:** Усиливает градиенты от редких, но критичных токенов (`base64`, `4444`, `-e`), смещая границу в сторону уменьшения False Negative.

**DevOps-контекст:** В пайплайнах с текстовыми признаками всегда логируйте топ-20 весов модели — это помогает детектировать дрейф (например, если вес токена `eval` резко упал, возможно, атакующие сменили тактику).

**Команды:**
```python
# L1-регуляризация с отбором признаков
from sklearn.linear_model import LogisticRegression
clf_l1 = LogisticRegression(penalty='l1', solver='liblinear', C=0.1)

# L2 с class_weight для дисбаланса
clf_l2 = LogisticRegression(penalty='l2', C=1.0, class_weight='balanced')

# Визуализация весов после TF-IDF
import numpy as np
feature_names = vectorizer.get_feature_names_out()
weights = clf.coef_[0]
top_idx = np.argsort(np.abs(weights))[-20:][::-1]
for i in top_idx:
    print(f"{feature_names[i]:20s} {weights[i]:+.4f}")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🛠️ Feature Engineering & Работа с данными

## 6. `Family_Survival` в Titanic: это data leakage? Как правильно валидировать?

**Кратко:** Да, это классический **target leakage**. Вычисление `min/max Survived` внутри групп по `Last_Name + Fare` использует информацию из таргета, которая недоступна в продакшене.

**Подробно:**
- 🔹 **Почему это leakage:** Если в тесте есть пассажир из семьи, где в трейне кто-то выжил, его признак `Family_Survival` станет `1`. Модель фактически получает ответ.
- 🔹 **В продакшене невозможно:** При поступлении нового пассажира у вас нет информации о выживших членах его семьи.

**Как правильно валидировать:**
1. **Fold-wise computation:** Внутри каждого фолда CV считай групповые статистики **только на train-части**, затем трансформируй val-часть.
2. **Bayesian smoothing / Target Encoding with CV:** Замени `min/max` на среднюю вероятность выживания семьи, посчитанную через OOF-схему.
3. **Продакшен-безопасный вариант:** Использовать только исторические признаки (размер семьи, класс каюты), а `Family_Survival` исключить.

**DevOps-контекст:** Любой признак, вычисляемый через таргет, **обязан** считаться внутри CV-фолдов. Иначе это не feature engineering, а «подглядывание в тест».

**Команды:**
```python
# Правильный OOF target encoding для групповых признаков
from sklearn.model_selection import StratifiedKFold
import numpy as np

def oof_target_encode(df, group_cols, target_col, k=5):
    df = df.copy()
    df['oof_te'] = np.nan
    skf = StratifiedKFold(n_splits=k, shuffle=True, random_state=42)
    
    for train_idx, val_idx in skf.split(df, df[target_col]):
        train = df.iloc[train_idx]
        # Считаем среднее по группе ТОЛЬКО на трейне
        te_map = train.groupby(group_cols)[target_col].mean()
        # Применяем к валидации
        df.loc[val_idx, 'oof_te'] = df.loc[val_idx].set_index(group_cols).index.map(te_map)
    
    # Заполняем пропуски глобальным средним
    df['oof_te'].fillna(df[target_col].mean(), inplace=True)
    return df['oof_te']
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 7. Энтропия Шеннона и χ²-тест в DGA. Почему они информативнее длины строки?

**Кратко:** Энтропия измеряет непредсказуемость распределения символов, χ² — отклонение от естественного языка. ДГ-домены «шумят» математически, длина — лишь поверхностный артефакт.

**Подробно:**
- **Шэнноновская энтропия:** `H(X) = −∑ p_i·log₂(p_i)`. Легитимные домены: `H ≈ 2.5–3.5` (фонетика языка). DGA: `H ≈ 4.0–4.5` (почти равномерное распределение).
- **χ²-тест:** `χ² = ∑ (O_c − E_c)² / E_c`, где `E_c = ENGLISH_FREQ[c] × L`. DGA сильно отклоняются от частот английского → высокий χ².

**Почему лучше длины:** Длину легко спамить (`verylonglegitcompany.com` vs `a1b2c3.com`). Энтропия и χ² измеряют **структурную случайность** — следствие алгоритмической генерации.

**DevOps-контекст:** В пайплайнах детекции новых угроз добавляйте мониторинг распределения `entropy` и `chi_square` — резкий сдвиг может сигнализировать о новом DGA-генераторе.

**Команды:**
```python
from math import log2
from collections import Counter

def calculate_entropy(s):
    if len(s) == 0: return 0
    probs = [cnt/len(s) for cnt in Counter(s).values()]
    return -sum(p * log2(p) for p in probs if p > 0)

def chi_square_score(name, english_freq):
    if len(name) == 0: return 0
    observed = Counter(name.lower())
    chi_sq = sum((observed.get(c,0) - english_freq.get(c,0.001)*len(name))**2 
                 / max(english_freq.get(c,0.001)*len(name), 0.001)
                 for c in set(name.lower()))
    return chi_sq / len(name)

# English frequencies для χ²
ENGLISH_FREQ = {'e':0.127,'t':0.091,'a':0.082,'o':0.075,'i':0.070, ...}
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 8. Почему `word` + `char_wb` n-grams в Bind/Shell & HTTP Malware?

**Кратко:** `word` ловит семантические токены (`curl`, `base64`), `char_wb` устойчив к обфускации (`\x41`, `nc-l`). Вместе = покрытие 95%+ паттернов.

**Подробно:**
|Анализатор|Что ловит|Когда критичен|
|----------|---------|-------------|
|`word` (1-4 grams)|Ключевые утилиты, флаги, известные сигнатуры|Чистые команды, известные атаки|
|`char_wb` (4-8 grams)|Субтокенные паттерны, обфускация, слитные флаги|Новые/мутировавшие атаки, эвазия|

**`char_wb` vs `char`:** `char_wb` добавляет пробелы по границам слов: `curl` → `c`, `cu`, `cur`, `curl`, `url`, `rl`, `l`. Это снижает «внутрисловной» шум, сохраняя чувствительность к мутациям.

**DevOps-контекст:** В SOC-пайплайнах комбинируйте оба анализатора с разным `min_df`: `word: min_df=3` (стабильные токены), `char_wb: min_df=5` (устойчивость к шуму).

**Команды:**
```python
from sklearn.feature_extraction.text import TfidfVectorizer

# Word-level: семантика
word_vec = TfidfVectorizer(
    analyzer='word', ngram_range=(1,4), max_features=5000,
    min_df=3, max_df=0.95, sublinear_tf=True
)

# Char-level с границами слов: устойчивость к обфускации
char_vec = TfidfVectorizer(
    analyzer='char_wb', ngram_range=(4,8), max_features=10000,
    min_df=5, max_df=0.90, sublinear_tf=True
)

# Объединение через hstack
from scipy.sparse import hstack
X_combined = hstack([word_vec.fit_transform(texts), char_vec.fit_transform(texts)])
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 9. Как бороться с разреженностью после TF-IDF?

**Кратко:** Не боритесь с разреженностью, если модель её понимает. Боритесь только когда она мешает (деревья, нейросети) или когда память/латентность критичны.

**Подробно:**
|Метод|Когда применять|Плюсы|Минусы|
|-----|--------------|-------|-------|
|**Регуляризация (L1/L2)**|LR/LinearSVC, модель поддерживает sparse|Не теряет информацию, авто-отбор шума|Не работает с деревьями|
|**`SelectKBest` (chi2)**|Перед деревьями, нужен явный отбор|Быстро, интерпретируемо|Может отбросить коррелированные признаки|
|**`TruncatedSVD` (LSA)**|Перед нейросетями, нужна плотная репрезентация|Снижает размерность, выявляет темы|Теряет интерпретируемость|
|**`HashingVectorizer`**|Потоковая обработка, нет места под словарь|Stateless, не хранит словарь|Коллизии хешей, нельзя `inverse_transform`|

**DevOps-контекст:** В продакшене с >50k признаков всегда добавляйте `SelectKBest` или `TruncatedSVD` перед LightGBM/XGBoost — иначе `.toarray()` съест всю память.

**Команды:**
```python
# Для линейных моделей — оставляем sparse
from sklearn.linear_model import LogisticRegression
clf = LogisticRegression(penalty='l2', C=1.0)  # работает с scipy.sparse

# Для деревьев — отбор признаков
from sklearn.feature_selection import SelectKBest, chi2
selector = SelectKBest(chi2, k=2000)
X_selected = selector.fit_transform(X_tfidf, y)

# Для нейросетей — SVD до плотного представления
from sklearn.decomposition import TruncatedSVD
svd = TruncatedSVD(n_components=200, random_state=42)
X_dense = svd.fit_transform(X_tfidf)  # теперь можно .toarray()
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 10. Нормализация пакетов в `Who's Talking`: `/1500.0` + split на size/direction. Зачем?

**Кратко:** Нормализация контролирует динамику градиентов. Разделение `size`/`direction` = явное кодирование доменной логики, которую сеть иначе учила бы дольше.

**Подробно:**
- **Проблема raw-значений:** `tcp_len ∈ [-1500, +1500]` → большие градиенты → нестабильное обучение, риск `NaN` в `float16`.
- **`/1500.0`:** Масштабирует в `[-1, 1]` → градиенты сопоставимы с весами → быстрее сходимость, стабильнее `BatchNorm`.
- **Split на `size = |x|` и `direction = sign(x)`:** CNN легче учить паттерны, когда магнитуда и направление разделены. Например: `большой_наружу → маленький_внутрь` становится явной последовательностью.

**DevOps-контекст:** В пайплайнах обработки сетевого трафика всегда нормализуйте числовые признаки перед подачей в нейросеть. Логируйте распределение после нормализации — сдвиг может сигнализировать о дрейфе протоколов.

**Команды:**
```python
import numpy as np

def preprocess_packets(df, packet_cols):
    X = df[packet_cols].values.astype(np.float32)
    
    # Нормализация к [-1, 1]
    X = X / 1500.0
    
    # Разделение на размер и направление
    size = np.abs(X)
    direction = np.sign(X)
    
    # Стек в каналы: (batch, 30, 2)
    X = np.stack([size, direction], axis=-1)
    return X

# Для float16 оптимизации (только если модель поддерживает)
X_fp16 = preprocess_packets(df, cols).astype(np.float16)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🧠 Модели & Алгоритмы

## 11. Как работает 1D-CNN в `Who's Talking`? Почему свёртки эффективнее Dense/RNN?

**Кратко:** 1D-свёртка «сканирует» последовательность пакетов на наличие локальных паттернов. Параллельна, инвариантна к сдвигу, требует мало параметров — идеально для коротких сетевых последовательностей.

**Подробно:**
|Архитектура|Плюсы|Минусы|Когда использовать|
|-----------|-------|-------|-----------------|
|**Dense**|Просто, быстро для малых данных|Игнорирует порядок, много параметров|Табличные признаки, нет последовательности|
|**RNN/LSTM**|Учитывает долгосрочные зависимости|Медленно, затухание градиентов|Длинные последовательности (>100 шагов)|
|**1D-CNN**|Параллельна, ловит локальные паттерны, мало параметров|Не видит глобальный контекст без pooling|Короткие фиксированные последовательности (10-50 шагов)|

**Роль `padding='same'`:** Сохраняет длину последовательности после свёртки → можно безопасно стекать слои без потери информации на границах.

**Роль `GlobalAveragePooling1D`:** Сжимает `(batch, 30, filters)` → `(batch, filters)` усреднением. Заменяет `Flatten()` (который дал бы `30×256=7680` признаков), делает модель инвариантной к положению паттерна.

**DevOps-контекст:** В продакшене 1D-CNN для трафика даёт ×5-10 ускорение инференса по сравнению с LSTM при сопоставимой точности. Всегда используйте `GlobalAveragePooling` вместо `Flatten` для экономии памяти.

**Команды:**
```python
import tensorflow as tf
from tensorflow.keras import layers

def create_1d_cnn(input_shape=(30, 2), num_classes=10):
    inp = tf.keras.Input(shape=input_shape)
    
    # Стек свёрток с BatchNorm
    x = layers.Conv1D(64, 3, padding='same', activation='relu')(inp)
    x = layers.BatchNormalization()(x)
    
    x = layers.Conv1D(128, 3, padding='same', activation='relu')(x)
    x = layers.BatchNormalization()(x)
    
    x = layers.Conv1D(256, 3, padding='same', activation='relu')(x)
    x = layers.BatchNormalization()(x)
    
    # Global pooling вместо flatten
    x = layers.GlobalAveragePooling1D()(x)
    
    # Dense-головка с dropout
    x = layers.Dense(256, activation='relu')(x)
    x = layers.Dropout(0.4)(x)
    out = layers.Dense(num_classes, activation='softmax', dtype='float32')(x)
    
    return tf.keras.Model(inp, out)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 12. Что такое `Ordered Boosting` в CatBoost и как он снижает переобучение?

**Кратко:** Ordered Boosting встраивает логику кросс-валидации прямо в процесс обучения: градиенты для объекта вычисляются только по объектам, стоящим до него в случайной перестановке.

**Подробно:**
- 🔹 **Проблема классического GBM:** Градиенты вычисляются на всём тренировочном наборе → дерево «подсматривает» в ответы → target leakage → переобучение.
- 🔹 **Как работает Ordered Boosting:**
  1. Генерируется случайная перестановка тренировочных объектов
  2. Для объекта `i` градиент вычисляется **только по объектам до него** в перестановке
  3. Дерево строится на этих «out-of-sample» градиентах

**Связь с целевым кодированием:** CatBoost кодирует категории, вычисляя среднее по таргету **только для предыдущих объектов** в той же перестановке. Это гарантирует, что и градиенты, и категориальные фичи вычисляются без заглядывания в будущее.

**DevOps-контекст:** В пайплайнах с табличными данными CatBoost часто выигрывает «из коробки» именно благодаря Ordered Boosting — не требуется ручная настройка CV-схем для предотвращения leakage.

**Команды:**
```python
from catboost import CatBoostClassifier, Pool

# Ordered Boosting включён по умолчанию
model = CatBoostClassifier(
    iterations=1500,
    learning_rate=0.1,
    depth=6,
    loss_function='Logloss',
    eval_metric='AUC',
    task_type='CPU',  # или 'GPU'
    verbose=50,
    random_seed=42,
    early_stopping_rounds=150,
    use_best_model=True,
    # Ordered Boosting:
    # bootstrap_type='Bernoulli'  # для дополнительного контроля
)

# Обучение с eval_set для early stopping
model.fit(
    X_train, y_train,
    eval_set=(X_val, y_val),
    plot=False  # True для визуализации в Jupyter
)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 13. Математическое отличие LinearSVC от Logistic Regression. Когда они совпадают, а когда SVM лучше?

**Кратко:** LR минимизирует логарифмическую потерь (моделирует вероятности), SVM — hinge loss (максимизирует зазор). При слабой регуляризации и сбалансированных данных сходятся к одной гиперплоскости.

**Подробно:**
|Аспект|Logistic Regression|LinearSVC|
|------|-----------------|---------|
|**Функция потерь**|Log-loss: `log(1+exp(-y·wᵀx))`|Hinge loss: `max(0, 1-y·wᵀx)`|
|**Выход**|Вероятности `P(Y=1\|X)`|Расстояние до гиперплоскости|
|**Чувствительность к выбросам**|Высокая (штрафует даже правильные с низкой уверенностью)|Низкая (игнорирует объекты с `y·wᵀx > 1`)|
|**Калиброванность**|Высокая по природе|Низкая, требует `CalibratedClassifierCV`|

**Когда предсказания идентичны:** При большом `C` (слабая регуляризация), сбалансированных данных и отсутствии сильных выбросов обе модели сходятся к почти одинаковой гиперплоскости.

**Преимущество SVM:** Устойчивость к выбросам + эффективность в высокоразмерных пространствах (после TF-IDF) за счёт поиска только опорных векторов.

**DevOps-контекст:** В текстовых пайплайнах с разреженными признаками LinearSVC часто даёт +0.01-0.02 к F1 по сравнению с LR, но требует калибровки для корректного усреднения в ансамблях.

**Команды:**
```python
# Logistic Regression — вероятности из коробки
from sklearn.linear_model import LogisticRegression
lr = LogisticRegression(C=0.5, class_weight='balanced', solver='lbfgs')
lr_proba = lr.fit(X, y).predict_proba(X)[:, 1]

# LinearSVC — нужна калибровка для вероятностей
from sklearn.svm import LinearSVC
from sklearn.calibration import CalibratedClassifierCV
svc = LinearSVC(C=0.5, class_weight='balanced', max_iter=3000)
svc_calibrated = CalibratedClassifierCV(svc, method='sigmoid', cv=5)
svc_proba = svc_calibrated.fit(X, y).predict_proba(X)[:, 1]

# Сравнение границ
import numpy as np
correlation = np.corrcoef(lr_proba, svc_proba)[0, 1]
print(f"Correlation between LR and SVC probabilities: {correlation:.4f}")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 14. Почему LightGBM использует `leaf-wise` рост? Почему нужен жёсткий контроль?

**Кратко:** `leaf-wise` растит дерево асимметрично, выбирая на каждом шаге лист с наибольшим уменьшением потерь. Быстрее и точнее, но без контроля (`max_depth`, `num_leaves`) ведёт к тяжёлому переобучению.

**Подробно:**
|Стратегия|Как работает|Плюсы|Минусы|
|---------|-----------|-------|-------|
|**`level-wise`** (XGBoost)|Растёт симметрично по уровням|Безопасно, предсказуемо|Тратит вычисления на малополезные ветки|
|**`leaf-wise`** (LightGBM)|Выбирает один лучший лист для разбиения|Фокусирует ресурсы, быстрее сходится|Может вырастить «иглу» на шумной подвыборке|

**Почему требует контроля:** Без ограничений `leaf-wise` может вырастить глубокую ветку на маленькой шумной подвыборке → высокий variance. Критичны:
- `max_depth`: ограничивает глубину дерева
- `min_data_in_leaf`: запрещает разбивать лист с малым числом объектов
- `min_gain_to_split`: требует минимального улучшения для разбиения

**DevOps-контекст:** В CI/CD для ML всегда фиксируйте `max_depth` и `num_leaves` в конфиге модели — это предотвращает «тихое» переобучение при изменении данных.

**Команды:**
```python
import lightgbm as lgb

# Безопасная конфигурация leaf-wise
model = lgb.LGBMClassifier(
    n_estimators=500,
    learning_rate=0.03,      # Низкий LR для стабильности
    max_depth=10,            # Ограничение глубины
    num_leaves=50,           # Ограничение числа листьев
    min_data_in_leaf=50,     # Минимум объектов в листе
    min_gain_to_split=0.01,  # Минимальное улучшение
    class_weight='balanced',
    random_state=42,
    verbose=-1
)

# Мониторинг переобучения через early stopping
model.fit(
    X_train, y_train,
    eval_set=[(X_val, y_val)],
    callbacks=[
        lgb.early_stopping(stopping_rounds=50),
        lgb.log_evaluation(period=50)
    ]
)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 15. Как работает Batch Normalization? Зачем он после каждого Conv1D?

**Кратко:** BN стабилизирует распределение входов каждого слоя, сглаживая ландшафт функции потерь → позволяет больший LR, ускоряет сходимость, работает как лёгкий регуляризатор.

**Подробно:**
- **Механика:** Для каждого канала вычисляет `μ` и `σ²` по батчу, нормализует: `x̂ = (x - μ) / √(σ² + ε)`, затем применяет обучаемые `γ, β`: `y = γ·x̂ + β`.
- **Зачем после каждого Conv1D:**
  1. Сглаживает ландшафт функции потерь → больший `learning_rate` без расходимости
  2. Ускоряет сходимость: градиенты не «взрываются» при прохождении через слои
  3. Регуляризация: шум от статистик батча добавляет стохастический эффект

**Влияние маленького `batch_size`:** BN опирается на статистику батча. При `batch_size < 32` оценки `μ` и `σ` становятся шумными → дестабилизация. В таких случаях используют `GroupNorm` или `LayerNorm`.

**DevOps-контекст:** В продакшене с маленьким батчем (например, edge-устройства) замените `BatchNormalization` на `LayerNormalization` — он не зависит от размера батча.

**Команды:**
```python
from tensorflow.keras import layers

# Стандартный паттерн: Conv → BN → Activation
x = layers.Conv1D(64, 3, padding='same')(inp)
x = layers.BatchNormalization()(x)  # Стабилизирует выход свёртки
x = layers.Activation('relu')(x)

# Для маленьких батчей (<32) используйте LayerNorm
x = layers.Conv1D(64, 3, padding='same')(inp)
x = layers.LayerNormalization()(x)  # Не зависит от batch_size
x = layers.Activation('relu')(x)

# В инференсе: BN использует скользящие средние, не статистику батча
# Это важно для консистентности train/infer
model.predict(X_test, batch_size=1)  # Работает корректно
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 📊 Валидация, Метрики & Пороговая оптимизация

## 16. Почему в `DGA` ты оптимизировал Fβ=0.5, а в `Bind/Shell` и `HTTP Malware` — F1? Приоритет Precision vs Recall в Security

**Кратко:** `β` — это переводчик бизнес-требований на язык метрик. В Security `β<1` (Precision важнее), в Медицине `β>1` (Recall важнее).

**Подробно:**
- **Формула:** `Fβ = (1+β²)·P·R / (β²·P + R)`
- **Математика баланса:**
  - `β=1` → `F1`: Precision и Recall равнозначны
  - `β<1` → Precision получает больший вес: при `β=0.5`, `β²=0.25` → низкий Precision «штрафуется» в 4 раза сильнее
  - `β>1` → Recall приоритетнее

**Почему `F0.5` в DGA:** Блокировка легитимного домена (FP) = простой бизнеса, жалобы, ручной разбор. Лучше пропустить 10-15% DGA, чем запороть 5% реального трафика.

**Почему `F1` в Bind/Shell и HTTP Malware:** В соревнованиях метрика была `F1`. На практике для детекции шеллов/малвари тоже важен баланс: слишком высокий порог пропустит атаки, слишком низкий захлебнёт SOC ложными алертами.

|Метрика|Когда приоритетнее|Пример|
|-------|-----------------|--------|
|**Precision**|Высокая цена FP, ограниченная команда аналитиков|Блокировка доменов, спам-фильтры, L1 SOC алерты|
|**Recall**|Критично не пропустить угрозу, можно разбирать много ложных|EDR на хостах, песочницы, детекция APT|

**DevOps-контекст:** Всегда начинайте настройку метрики с вопроса: «Какова стоимость одного FP и одного FN в вашем контексте?». Затем выбирайте `β = √(C_FP / C_FN)`.

**Команды:**
```python
from sklearn.metrics import fbeta_score, precision_recall_curve
import numpy as np

def find_optimal_threshold(y_true, y_proba, beta=0.5):
    """Найти порог, максимизирующий Fβ"""
    precisions, recalls, thresholds = precision_recall_curve(y_true, y_proba)
    # Избегаем деления на ноль
    f2_scores = (1 + beta**2) * precisions * recalls / (beta**2 * precisions + recalls + 1e-10)
    optimal_idx = f2_scores.argmax()
    optimal_threshold = thresholds[optimal_idx] if optimal_idx < len(thresholds) else 0.5
    return optimal_threshold, f2_scores[optimal_idx]

# Использование
threshold, best_fbeta = find_optimal_threshold(y_val, y_proba_val, beta=0.5)
print(f"Optimal threshold for F0.5: {threshold:.4f}, score: {best_fbeta:.4f}")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 17. Как работает Out-of-Fold (OOF) валидация? Почему надёжнее `train_test_split` для порога?

**Кратко:** В OOF каждый объект предсказан моделью, которая его не видела. Это даёт честную оценку обобщающей способности и реалистичное распределение вероятностей для настройки порога.

**Подробно:**
- **Механика:** В `K`-fold CV модель обучается `K` раз. На каждой итерации `K-1` фолдов → `train`, 1 фолд → `val`. Предсказания на валидационных фолдах конкатенируются → вектор `oof_proba` длины `len(X_train)`.
- **Почему надёжнее для порога:**
  1. **Нет data leakage:** Обычный `train_test_split` даёт только ~20-30% данных для валидации. OOF использует 100% тренировочных данных, сохраняя out-of-sample честность.
  2. **Снижает дисперсию:** Метрика на одном сплите может «повезти» или «не повезти». OOF усредняет результат по `K` разным разбиениям.
  3. **Реалистичное распределение вероятностей:** Модель склонна к overconfidence на тренировочных данных. `oof_proba` имитирует тестовое распределение → порог обобщается.

**DevOps-контекст:** Порог, найденный по OOF — это единственный честный способ настроить бизнес-правило без участия публичного LB. Всегда логируйте `oof_proba` для последующего анализа дрейфа.

**Команды:**
```python
from sklearn.model_selection import StratifiedKFold
from sklearn.linear_model import LogisticRegression
import numpy as np

def get_oof_proba(X, y, model_class, params, n_splits=5):
    """Получить OOF вероятности для настройки порога"""
    skf = StratifiedKFold(n_splits=n_splits, shuffle=True, random_state=42)
    oof_proba = np.zeros(len(X))
    
    for train_idx, val_idx in skf.split(X, y):
        X_tr, X_val = X[train_idx], X[val_idx]
        y_tr = y.iloc[train_idx] if hasattr(y, 'iloc') else y[train_idx]
        
        model = model_class(**params)
        model.fit(X_tr, y_tr)
        
        # Предсказания на валидации (out-of-sample)
        oof_proba[val_idx] = model.predict_proba(X_val)[:, 1]
    
    return oof_proba

# Использование для оптимизации порога
oof_proba = get_oof_proba(X_train, y_train, LogisticRegression, {'C': 1.0})
threshold, _ = find_optimal_threshold(y_train, oof_proba, beta=0.5)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 18. Калибровка вероятностей (Platt, Isotonic). Зачем перед усреднением LR + LGBM?

**Кратко:** Выходы моделей — не истинные вероятности. Калибровка приводит их к единой шкале, после чего арифметическое среднее имеет статистический смысл.

**Подробно:**
|Модель|Выход по умолчанию|Проблема|Решение|
|------|-----------------|--------|-------|
|**LogisticRegression**|Откалибрована по природе|Может смещаться при дисбалансе|`class_weight='balanced'`|
|**LightGBM/CatBoost**|«Скоры», прижатые к 0/1|Overconfident, плохая калибровка|`CalibratedClassifierCV`|
|**LinearSVC**|Расстояния до гиперплоскости|Вообще не вероятности|`CalibratedClassifierCV(method='sigmoid')`|

**Методы калибровки:**
- **Platt Scaling:** Фитит логистическую регрессию `σ(As+B)` на скоры модели. Параметрическая, быстрая, хорошо работает при малом объёме данных.
- **Isotonic Regression:** Фитит монотонную кусочно-постоянную функцию. Непараметрическая, гибкая, но требует больше данных.

**Зачем перед ансамблированием:** Без калибровки:
- LR даёт `0.65` (реальная вероятность ~0.65)
- LGBM даёт `0.92` (реальная вероятность ~0.65, но overconfident)
- Среднее = `0.785` → смещено вверх → порог 0.5 даст лишние FP.

**DevOps-контекст:** В продакшене всегда калибруйте вероятности перед подачей в бизнес-правила или ансамбли. Логируйте калибровочные кривые для мониторинга деградации.

**Команды:**
```python
from sklearn.calibration import CalibratedClassifierCV
from sklearn.linear_model import LogisticRegression
import lightgbm as lgb

# Калибровка для LightGBM
base_lgb = lgb.LGBMClassifier(n_estimators=500, learning_rate=0.03)
calibrated_lgb = CalibratedClassifierCV(
    base_lgb, method='sigmoid', cv=5, n_jobs=-1
)
calibrated_lgb.fit(X_train, y_train)

# Проверка калибровки
from sklearn.calibration import calibration_curve
import matplotlib.pyplot as plt

y_proba = calibrated_lgb.predict_proba(X_val)[:, 1]
prob_true, prob_pred = calibration_curve(y_val, y_proba, n_bins=10)

plt.plot(prob_pred, prob_true, marker='o', label='Calibrated')
plt.plot([0, 1], [0, 1], linestyle='--', label='Ideal')
plt.xlabel('Predicted probability')
plt.ylabel('True probability')
plt.legend()
plt.title('Calibration curve')
plt.show()
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 19. Почему Accuracy бессмыслен при дисбалансе, а PR-AUC информативнее ROC-AUC? Пример `Bind/Shell`

**Кратко:** При дисбалансе `Accuracy` вводит в заблуждение, `ROC-AUC` может быть оптимистичным из-за большого числа TN. `PR-AUC` честно показывает качество детекции редкого класса.

**Подробно:**
- **Accuracy:** `Bind/Shell`: ~9320 clean, ~202 malicious (97.8% / 2.2%). Dummy-модель «всегда 0» даст **Accuracy = 97.8%**, но **не найдёт ни одной атаки**.
- **ROC-AUC:** Ось X = `FPR = FP/(FP+TN)`. При `TN ≈ 9000` даже 50 ложных срабатываний дают `FPR ≈ 0.0055`. ROC-кривая почти не двигается по горизонтали → модель с сотнями FP может показать `ROC-AUC = 0.95`, создавая иллюзию качества.
- **PR-AUC:** Ось Y = `Precision = TP/(TP+FP)`. Базовая линия = доля позитивов = **0.022**. Любое увеличение FP сразу бьёт по Precision.

**Когда что смотреть:**
|Метрика|Что измеряет|Когда использовать|
|-------|-----------|-----------------|
|**Accuracy**|Доля верных ответов|Сбалансированные данные, все классы равнозначны|
|**ROC-AUC**|Способность ранжировать объекты|Сравнение моделей, сбалансированный или умеренный дисбаланс|
|**PR-AUC**|Качество детекции редкого класса|Сильный дисбаланс (>1:10), приоритет на minority class|
|**Fβ**|Бизнес-взвешенный баланс|Когда известна стоимость FP/FN|

**DevOps-контекст:** В дашбордах мониторинга моделей всегда показывайте `PR-AUC` и `Fβ` для редких классов. `Accuracy` и `ROC-AUC` оставляйте для общего контекста.

**Команды:**
```python
from sklearn.metrics import (
    accuracy_score, roc_auc_score, average_precision_score,
    precision_recall_curve, auc
)

# Все метрики для оценки
print(f"Accuracy:  {accuracy_score(y_true, y_pred):.4f}")
print(f"ROC-AUC:   {roc_auc_score(y_true, y_proba):.4f}")
print(f"PR-AUC:    {average_precision_score(y_true, y_proba):.4f}")

# Ручной расчёт PR-AUC для визуализации
precisions, recalls, _ = precision_recall_curve(y_true, y_proba)
pr_auc = auc(recalls, precisions)
print(f"PR-AUC (manual): {pr_auc:.4f}")

# Визуализация
import matplotlib.pyplot as plt
plt.plot(recalls, precisions, label=f'PR curve (AUC={pr_auc:.2f})')
plt.axhline(y=y_true.mean(), color='gray', linestyle='--', label='Baseline')
plt.xlabel('Recall')
plt.ylabel('Precision')
plt.title('Precision-Recall Curve')
plt.legend()
plt.show()
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 20. Как оценивать модель при сдвиге распределения? (Covariate shift, Prior shift)

**Кратко:** Различайте типы сдвигов: `Covariate shift` (P(X) меняется), `Prior shift` (P(Y) меняется), `Concept shift` (P(Y|X) меняется). Для каждого — своя стратегия детекции и адаптации.

**Подробно:**
|Тип сдвига|Что меняется|Пример в Security|Как детектировать|
|----------|-----------|----------------|----------------|
|**Covariate**|P(X) | Новые протоколы, TLS 1.3, IPv6|PSI, KS-test для признаков|
|**Prior**|P(Y) | Всплеск кампаний (Log4Shell)|Сдвиг доли предсказаний `1`|
|**Concept**|P(Y\|X) | Новые DGA-алгоритмы, обфускация|Падение F1 на свежих размеченных данных|

**Как правильно оценивать:**
1. **Не полагаться на один split.** Использовать `TimeSeriesSplit` или группировку по дням/источникам.
2. **Мониторинг дрейфа признаков:**
   - `PSI (Population Stability Index)` для категориальных/бинированных фич. `PSI > 0.2` → сильный дрейф.
   - `KS-test` / `Wasserstein distance` для непрерывных (энтропия, длина, `chi_sq`).
3. **Контроль калибровки:** Сравнивать распределение `oof_proba` (train) и `test_proba`. Сдвиг вправо/влево = prior shift. Изменение формы = covariate shift.
4. **Адаптивные пороги:** Если `P(Y)` растёт, порог можно немного снизить для сохранения Recall. Если падает — поднять для защиты Precision.

**DevOps-контекст:** В Security модель «живёт» 3-6 месяцев. Без MLOps-пайплайна (непрерывное обучение, мониторинг дрейфа, active learning) она превращается в legacy-сигнатуру.

**Команды:**
```python
# PSI для мониторинга дрейфа категориальных признаков
def calculate_psi(expected, actual, bucket_threshold=0.01):
    """Population Stability Index"""
    def _calculate_bucket_data(data):
        buckets = np.histogram(data, bins=10)[0]
        buckets = buckets / len(data)
        buckets = np.where(buckets < bucket_threshold, bucket_threshold, buckets)
        return buckets
    
    exp_buckets = _calculate_bucket_data(expected)
    act_buckets = _calculate_bucket_data(actual)
    psi = np.sum((act_buckets - exp_buckets) * np.log(act_buckets / exp_buckets))
    return psi

# KS-test для непрерывных признаков
from scipy.stats import ks_2samp
stat, p_value = ks_2samp(train_feature, test_feature)
if p_value < 0.05:
    print(f"⚠️  Significant drift detected (p={p_value:.4f})")

# Мониторинг распределения предсказаний
import numpy as np
train_proba_mean = np.mean(oof_proba)
test_proba_mean = np.mean(test_proba)
shift = test_proba_mean - train_proba_mean
print(f"Prior shift estimate: {shift:+.4f}")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🤝 Ансамбли & Комбинирование моделей

## 21. В чём разница между Voting, Stacking и Blending? Что реализовал ты?

**Кратко:** Voting = демократия экспертов (фиксированные правила), Stacking = менеджер, который учится доверять экспертам в разных ситуациях, Blending = упрощённый stacking с разделением данных.

**Подробно:**
|Метод|Как работает|Плюсы|Минусы|Когда использовать|
|-----|-----------|-------|-------|-----------------|
|**Voting**|Базовые модели предсказывают независимо, комбинация по правилу|Просто, нет риска leakage, стабильно|Не учится, какой модели доверять|Baseline, production с ограниченным пайплайном|
|**Stacking**|Выходы базовых моделей (OOF) → признаки для мета-модели|Учится комбинировать, потенциально выше точность|Сложнее, риск leakage при неправильной реализации|Большие данные, стабильный MLOps-пайплайн|
|**Blending**|Разделение на train/hold-out, мета-модель учится на hold-out|Быстро, проще чем stacking|Тратит часть данных, высокая дисперсия оценки|Прототипирование, когда данных много|

**Что реализовал ты:**
- В `bind-reverse`: `ensemble_preds = np.round(np.mean(all_preds, axis=0))` → **Hard Voting** на финальных метках.
- В `http-malware`: `oof_proba_ensemble = (oof_proba_lr + oof_proba_lgb) / 2` → **Soft Voting / Probability Averaging**.
- **Почему:** Простота, отсутствие риска leakage, стабильность на малых/средних данных. Мета-модель могла бы дать +0.005-0.01, но усложнила бы пайплайн без гарантии прироста.

**DevOps-контекст:** В production начинайте с Voting. Переходите к Stacking только при стабильном пайплайне, больших данных и доказанном приросте на hold-out.

**Команды:**
```python
# Soft Voting (Probability Averaging) — ваш подход
from sklearn.linear_model import LogisticRegression
import lightgbm as lgb
import numpy as np

# Обучение базовых моделей
lr = LogisticRegression(C=1.0, class_weight='balanced')
lgb_clf = lgb.LGBMClassifier(n_estimators=500, learning_rate=0.03)

lr.fit(X_train, y_train)
lgb_clf.fit(X_train, y_train)

# Усреднение вероятностей
proba_lr = lr.predict_proba(X_test)[:, 1]
proba_lgb = lgb_clf.predict_proba(X_test)[:, 1]
proba_ensemble = (proba_lr + proba_lgb) / 2

# Пороговая классификация
threshold = 0.52  # найденный по OOF
preds = (proba_ensemble >= threshold).astype(int)

# Stacking с OOF (без leakage)
from sklearn.model_selection import StratifiedKFold
from sklearn.linear_model import Ridge

def stacking_oof(X, y, base_models, meta_model, n_splits=5):
    skf = StratifiedKFold(n_splits=n_splits, shuffle=True, random_state=42)
    oof_preds = np.zeros((len(X), len(base_models)))
    
    for fold, (train_idx, val_idx) in enumerate(skf.split(X, y)):
        X_tr, X_val = X[train_idx], X[val_idx]
        y_tr = y.iloc[train_idx] if hasattr(y, 'iloc') else y[train_idx]
        
        for i, model in enumerate(base_models):
            m = clone(model)
            m.fit(X_tr, y_tr)
            oof_preds[val_idx, i] = m.predict_proba(X_val)[:, 1]
    
    # Обучение мета-модели на OOF
    meta_model.fit(oof_preds, y)
    return meta_model, oof_preds
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 22. Почему усреднение вероятностей (soft) стабильнее hard voting? Влияние корреляции ошибок.

**Кратко:** Soft voting сохраняет градацию уверенности, сглаживает резкие границы решений и математически эквивалентен усреднению логитов в пространстве вероятностей.

**Подробно:**
- **Математика уверенности:**
  - `Hard`: `[0, 1, 1] → 1`. Модель 1 была уверена на 51%, модель 2 на 99%, модель 3 на 88%. Все голоса равны.
  - `Soft`: `[0.51, 0.99, 0.88] → 0.79 → 1`. Уверенность пропорциональна вкладу.

- **Корреляция ошибок и дисперсия ансамбля:**
  - Если ошибки моделей **независимы**, дисперсия ансамбля падает как `1/N`.
  - Если модели делают **одинаковые ошибки** (высокая корреляция `ρ≈1`), дисперсия почти не снижается.
  - Формула (упрощённо): `Var_ens ≈ ρ·Var_base + (1-ρ)·Var_base/N`

**Почему soft voting лучше:**
1. Сглаживает резкие границы решений → снижает дисперсию
2. Позволяет двигать порог постфактум под бизнес-метрику
3. Математически эквивалентно усреднению логитов в пространстве вероятностей → ближе к истинному `P(Y|X)`

**DevOps-контекст:** В продакшене всегда сохраняйте `predict_proba`, а не только `predict`. Это позволяет менять порог без переобучения и анализировать калибровку модели.

**Команды:**
```python
# Сравнение hard vs soft voting
from sklearn.metrics import f1_score
import numpy as np

# Hard voting (равные голоса)
hard_preds = np.round(np.mean([preds_lr, preds_lgb], axis=0)).astype(int)
f1_hard = f1_score(y_val, hard_preds)

# Soft voting (усреднение вероятностей)
soft_proba = (proba_lr + proba_lgb) / 2
soft_preds = (soft_proba >= threshold).astype(int)
f1_soft = f1_score(y_val, soft_preds)

print(f"F1 Hard Voting: {f1_hard:.4f}")
print(f"F1 Soft Voting: {f1_soft:.4f}")

# Анализ корреляции ошибок
errors_lr = (preds_lr != y_val).astype(int)
errors_lgb = (preds_lgb != y_val).astype(int)
correlation = np.corrcoef(errors_lr, errors_lgb)[0, 1]
print(f"Error correlation: {correlation:.4f}")
# Если correlation < 0.5 → ансамбль даст заметный выигрыш
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 23. Почему LR + LGBM дают синергию? Какие паттерны ловит каждая?

**Кратко:** Линейная модель = «глобальный компас» (стабильный базовый прогноз), деревья = «локальные детекторы» (нелинейные взаимодействия). Их ошибки ортогональны → при усреднении bias остаётся низким, variance резко падает.

**Подробно:**
|Аспект|Logistic Regression|LightGBM|
|------|-----------------|--------|
|**Тип модели**|Линейная, аддитивная|Древовидная, нелинейная, иерархическая|
|**Что ловит**|Глобальные веса признаков (`keyword=malicious → +0.8`)|Локальные правила (`IF header="X" AND status=403 THEN malware`)|
|**Чувствительность к масштабу**|Высокая (требует нормализации)|Нулевая|
|**Работа с разреженностью**|Отличная (нативно + регуляризация)|Плохая (требует `.toarray()`, растёт память)|
|**Калиброванность**|Высокая по природе|Низкая (склонна к 0.0/1.0)|

**Синергия:**
- LR даёт **стабильный базовый прогноз** и хорошо интерпретируемые веса
- LGBM добавляет **нелинейные взаимодействия** и пороговые эффекты, которые линейная модель физически не может выразить
- Их ошибки **ортогональны**: где один «линеен», другой «ломает плоскость». При усреднении bias остаётся низким, а variance резко падает

**DevOps-контекст:** В продакшене логируйте веса LR и feature importance LGBM отдельно. Если важность признака резко меняется между моделями — это сигнал для анализа дрейфа или новых паттернов атак.

**Команды:**
```python
# Визуализация синергии: сравнение важности признаков
import matplotlib.pyplot as plt
import numpy as np

# Веса LR (после TF-IDF)
lr_weights = clf_lr.coef_[0]
lr_top_idx = np.argsort(np.abs(lr_weights))[-10:][::-1]

# Feature importance LGBM
lgb_importance = clf_lgb.feature_importances_
lgb_top_idx = np.argsort(lgb_importance)[-10:][::-1]

# Сравнение топ-10
feature_names = vectorizer.get_feature_names_out()
fig, axes = plt.subplots(1, 2, figsize=(14, 5))

axes[0].barh(range(10), np.abs(lr_weights[lr_top_idx])[::-1])
axes[0].set_yticks(range(10))
axes[0].set_yticklabels([feature_names[i] for i in lr_top_idx][::-1])
axes[0].set_title('Logistic Regression: Top 10 weights')

axes[1].barh(range(10), lgb_importance[lgb_top_idx][::-1])
axes[1].set_yticks(range(10))
axes[1].set_yticklabels([feature_names[i] for i in lgb_top_idx][::-1])
axes[1].set_title('LightGBM: Top 10 importance')

plt.tight_layout()
plt.show()
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 24. Что такое Stacked Generalization? Как избежать leakage при обучении мета-модели?

**Кратко:** Мета-модель не должна видеть `train_predictions`, полученные на тех же данных, на которых обучались базовые модели. Иначе она запомнит шум и переобучится.

**Подробно:**
- **Правильная схема (OOF Stacking):**
  1. Разбить `X_train, y_train` на `K` фолдов
  2. Для каждого фолда `k`:
     - Обучить базовые модели на `train \ fold_k`
     - Предсказать на `fold_k` → сохранить в `oof_preds`
  3. Сконкатенировать `oof_preds` → матрица мета-признаков `(N_train, n_models)`
  4. Обучить мета-модель **только на `oof_preds` + `y_train`**
  5. Для теста: обучить базовые модели на полном `train`, предсказать на `test`, подать в мета-модель

- **Типичная ошибка (Leakage 100%):**
  ```python
  # ❌ НЕПРАВИЛЬНО: мета-модель видит train-предсказания
  base_model.fit(X, y)
  meta_X = base_model.predict_proba(X)  # ← leakage!
  meta_model.fit(meta_X, y)
  ```

**DevOps-контекст:** В production-пайплайнах используйте готовые фреймворки (`mlens`, `vecstack`) или пишите OOF-логику с `StratifiedKFold`. Всегда валидируйте финальную метрику на независимом hold-out, не на OOF.

**Команды:**
```python
# Безопасный stacking с OOF
from sklearn.model_selection import StratifiedKFold
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier
from sklearn.linear_model import Ridge
import numpy as np

def safe_stacking(X, y, base_models, meta_model, n_splits=5):
    skf = StratifiedKFold(n_splits=n_splits, shuffle=True, random_state=42)
    n_models = len(base_models)
    oof_preds = np.zeros((len(X), n_models))
    
    # Генерация OOF предсказаний
    for fold, (train_idx, val_idx) in enumerate(skf.split(X, y)):
        X_tr, X_val = X[train_idx], X[val_idx]
        y_tr = y.iloc[train_idx] if hasattr(y, 'iloc') else y[train_idx]
        
        for i, model in enumerate(base_models):
            m = clone(model)
            m.fit(X_tr, y_tr)
            oof_preds[val_idx, i] = m.predict_proba(X_val)[:, 1]
    
    # Обучение мета-модели на OOF (без leakage!)
    meta_model.fit(oof_preds, y)
    
    # Подготовка к тесту: обучить базовые модели на полном train
    test_preds = np.zeros((len(X_test), n_models))
    for i, model in enumerate(base_models):
        m = clone(model)
        m.fit(X, y)
        test_preds[:, i] = m.predict_proba(X_test)[:, 1]
    
    # Финальное предсказание
    final_pred = meta_model.predict_proba(test_preds)[:, 1]
    return meta_model, final_pred

# Использование
base_models = [
    LogisticRegression(C=1.0, class_weight='balanced'),
    RandomForestClassifier(n_estimators=200, max_depth=10)
]
meta_model = Ridge(alpha=1.0)

meta_clf, test_proba = safe_stacking(X_train, y_train, base_models, meta_model)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 25. Как выбрать веса для взвешенного энсембля? Можно ли оптимизировать автоматически?

**Кратко:** Простое усреднение (`w=[0.5, 0.5]`) работает удивительно хорошо. Автоматическая оптимизация весов возможна, но редко даёт > +0.003 к тесту и рискует переобучением к валидационному распределению.

**Подробно:**
- **Простое усреднение:** `w = [0.5, 0.5]`. Работает удивительно хорошо, особенно если модели близки по CV-скорам.
- **Автоматическая оптимизация весов:**
  1. **Поиск по сетке на OOF:**
     ```python
     from scipy.optimize import minimize
     
     def neg_f1(w):
         w = np.abs(w) / np.sum(np.abs(w))  # нормализация
         preds = (w[0]*oof_lr + w[1]*oof_lgb >= thresh).astype(int)
         return -f1_score(y, preds)
     
     res = minimize(neg_f1, x0=[0.5, 0.5])
     ```
  2. **Линейная регрессия как мета-модель:** `Ridge().fit(oof_matrix, y)` → коэффициенты станут весами.
  3. **Optuna / Bayesian Optimization:** Максимизация метрики в пространстве `w ∈ [0,1], Σw=1`.

- **Подводные камни:**
  - Оптимизация весов на OOF всё ещё может дать **переобучение к валидационному распределению**
  - Если разница в CV-скорам < 0.01, оптимизация весов редко даёт > +0.003 к тесту
  - В продакшене проще зафиксировать веса и менять порог, чем постоянно перекалибровать ансамбль

**DevOps-контекст:** Фиксируйте веса ансамбля в конфиге, а порог настраивайте динамически по OOF. Это даёт гибкость без риска переобучения.

**Команды:**
```python
# Оптимизация весов через scipy.optimize
from scipy.optimize import minimize
from sklearn.metrics import f1_score
import numpy as np

def optimize_ensemble_weights(oof_preds_list, y_true, threshold=0.5, beta=1.0):
    """Найти веса, максимизирующие Fβ на OOF"""
    n_models = len(oof_preds_list)
    
    def neg_fbeta(w):
        w = np.abs(w) / np.sum(np.abs(w))  # нормализация к сумме 1
        ensemble_proba = np.sum([w[i] * oof_preds_list[i] for i in range(n_models)], axis=0)
        preds = (ensemble_proba >= threshold).astype(int)
        # Fβ score
        p = np.sum(preds * y_true) / (np.sum(preds) + 1e-10)
        r = np.sum(preds * y_true) / (np.sum(y_true) + 1e-10)
        fbeta = (1 + beta**2) * p * r / (beta**2 * p + r + 1e-10)
        return -fbeta
    
    # Начальные веса: равномерные
    x0 = np.ones(n_models) / n_models
    bounds = [(0, 1) for _ in range(n_models)]
    
    result = minimize(neg_fbeta, x0, bounds=bounds, method='L-BFGS-B')
    optimal_weights = np.abs(result.x) / np.sum(np.abs(result.x))
    
    return optimal_weights, -result.fun

# Использование
weights, best_fbeta = optimize_ensemble_weights(
    [oof_proba_lr, oof_proba_lgb], y_train, threshold=0.52, beta=0.5
)
print(f"Optimal weights: {weights}")
print(f"Best F0.5: {best_fbeta:.4f}")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# ⚡ Оптимизация, Память & Инференс

## 26. `float16` и `chunked inference` в `Who's Talking`. Влияние на точность/градиенты? Подводные камни смешанной точности?

**Кратко:** `float16` вдвое сокращает память и ускоряет матричные умножения на GPU. Но без контроля диапазона и корректного вывода последнего слоя модель либо «слепнет» (нулевые градиенты), либо «паникует» (NaN).

**Подробно:**
- **Диапазон `float16`:** ±6.1×10⁴, точность ~3 значащие цифры. Малые градиенты (<10⁻⁵) могут **обнулиться (underflow)**, большие → `inf/NaN` (overflow).
- **Влияние на точность и градиенты:**
  - В ручном касте `astype(np.float16)` авто-масштабирование потерь (Loss Scaling) не включается
  - Чтобы градиенты не исчезли, используйте `tf.keras.mixed_precision.set_global_policy('mixed_float16')`:
    - Динамически умножает loss на скаляр (напр. 1024)
    - Масштабирует градиенты обратно перед обновлением весов
    - На выходе `softmax` принудительно использует `float32`

**Подводные камни:**
1. **Batch Normalization:** Статистики `μ, σ` в `fp16` становятся шумными → нестабильное обучение при маленьком батче
2. **Накопление ошибок:** При 3+ слоях свёртки ошибка округления суммируется. Решение: хранить веса в `fp32`, вычисления в `fp16`, выходы критичных слоёв (`softmax`, `loss`) в `fp32`
3. **CPU/GPU несоответствие:** Если векторизация идёт на CPU в `fp64`, а модель на GPU в `fp16`, лишний кастинг съедает выигрыш в скорости

**DevOps-контекст:** В продакшене с GPU всегда используйте `mixed_float16` policy TensorFlow, а не ручной каст. Логируйте `NaN/inf` в градиентах для раннего детектирования проблем.

**Команды:**
```python
import tensorflow as tf
import numpy as np

# Правильная настройка mixed precision
policy = tf.keras.mixed_precision.Policy('mixed_float16')
tf.keras.mixed_precision.set_global_policy(policy)

# Модель с корректным выводом в float32
def create_model_mixed_precision(input_shape=(30, 2), num_classes=10):
    inp = tf.keras.Input(shape=input_shape)
    
    x = tf.keras.layers.Conv1D(64, 3, padding='same', activation='relu')(inp)
    x = tf.keras.layers.BatchNormalization()(x)
    
    x = tf.keras.layers.Conv1D(128, 3, padding='same', activation='relu')(x)
    x = tf.keras.layers.BatchNormalization()(x)
    
    x = tf.keras.layers.GlobalAveragePooling1D()(x)
    
    # Важно: последний Dense в float32 для стабильности softmax
    out = tf.keras.layers.Dense(num_classes, activation='softmax', dtype='float32')(x)
    
    return tf.keras.Model(inp, out)

# Chunked inference для экономии памяти
def predict_in_chunks(model, X_data, chunk_size=10000):
    preds = []
    for i in range(0, len(X_data), chunk_size):
        chunk = X_data[i:i+chunk_size]
        p = model.predict(chunk, batch_size=512, verbose=0)
        preds.append(p)
    return np.vstack(preds)

# Использование
model = create_model_mixed_precision()
test_proba = predict_in_chunks(model, X_test, chunk_size=50000)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 27. Почему в `Bind/Shell` матрицы приводились к `float32` перед `csr_matrix`? Что будет с `float64`?

**Кратко:** `scipy.sparse` по умолчанию использует `float64` (8 байт/элемент). Явный `astype(np.float32)` экономит **50% памяти** без потери точности для признаков.

**Подробно:**
- **Почему это критично:**
  - Разреженная матрица хранит не только значения, но и индексы строк/столбцов (`indices`, `indptr`). При `float64` общий оверхед растёт непропорционально.
  - Для 20 000 признаков × 10 000 строк разница: ~1.6 ГБ → ~0.8 ГБ. На Kaggle с лимитом 16 ГБ это разница между успешным обучением и `MemoryError`.
  - `scikit-learn`, `LightGBM` и `ONNX Runtime` оптимизированы под `float32`. `float64` может вызвать внутренние касты в C-расширениях, замедляя `fit()`/`predict()` на 10-20%.

- **Когда нужен `float64`:** Только для финансовой математики или физических симуляций, где важна 15-я цифра после запятой. В ML `float32` — «золотой стандарт».

**DevOps-контекст:** В пайплайнах с текстовыми признаками всегда явно указывайте `dtype=np.float32` при создании разреженных матриц. Логируйте размер матриц до/после кастинга для мониторинга потребления памяти.

**Команды:**
```python
from scipy.sparse import hstack, csr_matrix
import numpy as np

# Неправильно: неявный каст к float64
X_eng = extract_features(df)  # по умолчанию float64
X_sparse = csr_matrix(X_eng)  # теперь sparse с float64 → 8 байт/элемент

# Правильно: явный каст к float32 перед созданием sparse
X_eng = extract_features(df).astype(np.float32)  # 4 байта/элемент
X_sparse = csr_matrix(X_eng)  # sparse с float32 → экономия 50%

# Объединение с другими sparse матрицами
X_word = tfidf_word.transform(texts)  # уже float32
X_char = tfidf_char.transform(texts)  # уже float32
X_combined = hstack([X_word, X_char, X_sparse])  # все float32 → нет неявных кастов

# Проверка типа и размера
print(f"Matrix dtype: {X_combined.dtype}")  # должно быть float32
print(f"Memory usage: {X_combined.data.nbytes / 1e6:.2f} MB")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 28. Как работают `Early Stopping` и `ReduceLROnPlateau`? Как подбирать `patience`?

**Кратко:** `EarlyStopping` останавливает обучение при плато метрики, `ReduceLROnPlateau` уменьшает LR для «спуска» в более глубокий минимум. `patience` балансирует между временем обучения и риском недообучения.

**Подробно:**
|Параметр|Что делает|Как подбирать|Типичные значения|
|--------|---------|------------|----------------|
|**`patience` (EarlyStopping)**|Ждёт `patience` эпох без улучшения перед остановкой|Зависит от шума метрики и длительности эпохи|3-5 для больших стабильных датасетов, 7-15 для маленьких/шумных|
|**`patience` (ReduceLROnPlateau)**|Ждёт `patience` эпох перед уменьшением LR|Должен быть < patience EarlyStopping|1-3, чтобы LR успел снизиться до остановки|
|**`factor`**|Коэффициент уменьшения LR|Обычно 0.1-0.5|0.1 для агрессивного снижения, 0.5 для плавного|
|**`min_delta`**|Минимальное улучшение для сброса patience|Зависит от масштаба метрики|1e-4 для accuracy, 1e-3 для loss|

**Почему малый `patience` в `Who's Talking`:** При 8+ млн строк и `batch_size=512` метрика стабилизируется очень быстро. `patience=2` для EarlyStopping и `patience=1` для ReduceLROnPlateau оптимальны.

**DevOps-контекст:** В CI/CD для ML логируйте графики `train/val loss` для каждого запуска. Если `EarlyStopping` срабатывает слишком рано — увеличьте `patience`. Если модель переобучается — уменьшите.

**Команды:**
```python
import tensorflow as tf
from tensorflow.keras.callbacks import EarlyStopping, ReduceLROnPlateau

# Callbacks для стабильного обучения
callbacks = [
    EarlyStopping(
        monitor='val_loss',
        patience=2,              # ждать 2 эпохи без улучшения
        restore_best_weights=True,  # вернуть веса к лучшей эпохе
        mode='min',
        verbose=1
    ),
    ReduceLROnPlateau(
        monitor='val_loss',
        factor=0.1,              # уменьшить LR в 10 раз
        patience=1,              # ждать 1 эпоху перед снижением
        min_lr=1e-7,             # нижняя граница LR
        mode='min',
        verbose=1
    )
]

# Обучение
model.fit(
    X_train, y_train,
    validation_data=(X_val, y_val),
    epochs=50,
    batch_size=512,
    callbacks=callbacks
)

# Визуализация истории для анализа
import matplotlib.pyplot as plt
history = model.history  # или сохраните историю вручную

plt.figure(figsize=(12, 4))
plt.subplot(1, 2, 1)
plt.plot(history.history['loss'], label='Train loss')
plt.plot(history.history['val_loss'], label='Val loss')
plt.axvline(x=np.argmin(history.history['val_loss']), 
            color='red', linestyle='--', label='Best epoch')
plt.xlabel('Epoch')
plt.ylabel('Loss')
plt.legend()
plt.title('Loss curves')
plt.show()
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 29. Способы ускорения инференса TF-IDF + классификатор в продакшене

**Кратко:** Скорость = `(скорость векторизации) + (скорость модели)`. Оптимизация только модели без кэширования `Tfidf` даёт <10% выигрыша.

**Подробно:**
|Метод|Как работает|Плюсы|Минусы|Когда использовать|
|-----|-----------|-------|-------|-----------------|
|**Кэширование векторизатора**|Загрузка `TfidfVectorizer` из `joblib` один раз при старте сервиса|Мгновенный ответ, нет повторного `fit`|Занимает RAM под словарь (особенно при `max_features=10k+`)|Любой продакшен-сервис|
|**Батчинг запросов**|Накопление 32-128 запросов перед `transform`+`predict`|BLAS/GPU работают эффективнее|Увеличивает latency для одиночных запросов|Высоконагруженные API|
|**ONNX Runtime**|Конвертирует `sklearn` пайплайн в `.onnx`, исполняет на C++/CUDA|×3-10 ускорение, кроссплатформенность|Требует конвертации, не все фичи поддерживаются|Высокие требования к latency|
|**`HashingVectorizer`**|Stateless-векторизация (хеш-функция вместо словаря)|Не хранит словарь, потоковая обработка|Коллизии хешей, нельзя получить `inverse_transform`|Потоковая обработка, нет места под словарь|
|**Аппроксимация разреженности**|`TruncatedSVD` или `SelectKBest` до модели|Меньше признаков → быстрее инференс|Потеря информации, требует переобучения|Ограничения по памяти/латентности|

**DevOps-контекст:** В продакшене всегда кэшируйте векторизатор и модель. Для TF-IDF с >5000 признаков используйте `joblib.dump` с `compress=3` для баланса размера/скорости загрузки.

**Команды:**
```python
# Кэширование векторизатора и модели
import joblib
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.linear_model import LogisticRegression

# Сохранение
vectorizer = TfidfVectorizer(max_features=5000, ngram_range=(1,4))
X_train_vec = vectorizer.fit_transform(train_texts)
clf = LogisticRegression(C=1.0).fit(X_train_vec, y_train)

joblib.dump(vectorizer, 'vectorizer.pkl', compress=3)
joblib.dump(clf, 'model.pkl', compress=3)

# Загрузка в сервисе
vectorizer = joblib.load('vectorizer.pkl')
clf = joblib.load('model.pkl')

# Батчинг для ускорения
def predict_batch(texts, vectorizer, clf, batch_size=64):
    results = []
    for i in range(0, len(texts), batch_size):
        batch = texts[i:i+batch_size]
        X_batch = vectorizer.transform(batch)
        preds = clf.predict(X_batch)
        results.extend(preds)
    return results

# ONNX конвертация (для ещё большего ускорения)
from skl2onnx import convert_sklearn
from skl2onnx.common.data_types import StringTensorType

# Конвертация пайплайна (требуется кастомный векторизатор для ONNX)
onnx_model = convert_sklearn(clf, initial_types=[('input', StringTensorType([None]))])
with open('model.onnx', 'wb') as f:
    f.write(onnx_model.SerializeToString())

# Инференс через ONNX Runtime
import onnxruntime as ort
session = ort.InferenceSession('model.onnx')
# ... подготовка входных данных в формате ONNX
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 30. Как `gc.collect()` и `tf.keras.backend.clear_session()` влияют на память? Почему критичны в OOF-циклах?

**Кратко:** `gc.collect()` освобождает объекты без ссылок в Python-куче. `clear_session()` уничтожает граф вычислений TF и освобождает GPU-память. В OOF-циклах без очистки старые графы остаются как «зомби-объекты» → OOM.

**Подробно:**
- **`gc.collect()`:** Запускает сборщик мусора Python. Освобождает объекты, на которые не осталось ссылок (временные `numpy` массивы, `pandas` фреймы). Не чистит графические/С-расширения.
- **`tf.keras.backend.clear_session()`:** Уничтожает текущий граф вычислений TF, сбрасывает счётчики имён слоёв, очищает кэш оптимизаторов и **освобождает GPU/CPU память**, выделенную под веса и промежуточные тензоры.

**Почему критично в OOF-циклах:**
- В каждом фолде создаётся новая модель (`create_model()`). Без очистки старые графы остаются в памяти как «зомби-объекты».
- Kaggle лимит: ~16 ГБ RAM / 16 ГБ VRAM. После 2-3 фолдов 1D-CNN без `clear_session()` обычно падает с `OOM`.
- `gc.collect()` после `del model, val_pred` убирает фрагментацию в Python-куче, позволяя выделить большие сплошные блоки для следующего фолда.

**DevOps-контекст:** В продакшене с долгим временем жизни процесса (не Kaggle) `clear_session()` нужен реже, но `gc.collect()` полезен после обработки больших батчей для предотвращения фрагментации памяти.

**Команды:**
```python
import gc
import tensorflow as tf
from sklearn.model_selection import StratifiedKFold

def train_with_oof(X, y, create_model_fn, n_splits=5):
    skf = StratifiedKFold(n_splits=n_splits, shuffle=True, random_state=42)
    oof_proba = np.zeros(len(X))
    
    for fold, (train_idx, val_idx) in enumerate(skf.split(X, y), 1):
        print(f"Fold {fold}/{n_splits}")
        
        X_tr, X_val = X[train_idx], X[val_idx]
        y_tr, y_val = y.iloc[train_idx] if hasattr(y, 'iloc') else y[train_idx]
        
        # Создание и обучение модели
        model = create_model_fn()
        model.fit(X_tr, y_tr, validation_data=(X_val, y_val), epochs=10, verbose=0)
        
        # OOF предсказания
        oof_proba[val_idx] = model.predict(X_val, verbose=0)[:, 1]
        
        # 🔥 КРИТИЧЕСКАЯ ОЧИСТКА ПАМЯТИ 🔥
        del model
        tf.keras.backend.clear_session()  # Очистить граф TF и память
        gc.collect()  # Собрать мусор Python
    
    return oof_proba

# Использование
oof_results = train_with_oof(X_train, y_train, create_1d_cnn)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

# 🛡️ Специфика Кибербезопасности & Domain-Specific ML

## 31. Иерархическая логика: «1 транзакция = malware → файл = malware». Искажение метрик и правильная валидация

**Кратко:** Это классическая задача **Multiple Instance Learning (MIL)**. Вы обучаете модель на транзакциях, но предсказываете на уровне файлов по правилу `OR`. Валидация должна зеркалить продакшен-логику.

**Подробно:**
- **Как искажаются метрики:**
  - 🔹 **На уровне транзакций:** Модель может давать `F1 ≈ 0.85-0.90`. Но один `FP` на чистой транзакции превращает весь `clean` файл в `FP` → **Precision на файлах падает**.
  - 🔹 **На уровне файлов:** Даже если модель пропустила 3 из 4 вредоносных транзакций в файле, одна детектированная → файл помечен верно. Это искусственно **завышает Recall**, но делает модель крайне чувствительной к шуму.
  - 🔹 **Итог:** Метрики на транзакциях и файлах **не совпадают**. Оптимизация порога по транзакциям приведёт к завышенному числу алертов в SOC.

- **Как правильно валидировать:**
  1. **Группировка по `file_id`:** Все транзакции из одного файла должны попадать в один фолд CV. Иначе модель «подглядывает» паттерны файла.
  2. **Aggregation before scoring:** После получения `oof_proba` на транзакциях применяете `file_pred = any(tx_proba >= thresh)` → вычисляете `F1/Fβ` на файлах.
  3. **Стратификация по файлам:** `StratifiedGroupKFold` (если доступна) или ручная группировка, чтобы доля `malware`-файлов в фолдах совпадала.

**DevOps-контекст:** В продакшене логируйте метрики на обоих уровнях (транзакции/файлы). Если Precision на файлах падает при росте Recall на транзакциях — это сигнал о переобучении на шумные транзакции.

**Команды:**
```python
# Правильная валидация для MIL-задачи
import pandas as pd
import numpy as np
from sklearn.model_selection import GroupKFold

def validate_mil(df, tx_proba, file_id_col='file_id', label_col='label', threshold=0.5):
    """Валидация с агрегацией на уровне файлов"""
    # Агрегация: файл = malware, если хотя бы одна транзакция >= threshold
    df_agg = df.copy()
    df_agg['tx_proba'] = tx_proba
    df_agg['tx_pred'] = (df_agg['tx_proba'] >= threshold).astype(int)
    
    # Группировка по файлам
    file_preds = df_agg.groupby(file_id_col).agg({
        label_col: 'max',  # файл = malware, если хотя бы одна транзакция = malware
        'tx_pred': 'max'   # правило OR: any(tx_pred == 1)
    }).reset_index()
    
    # Метрики на уровне файлов
    from sklearn.metrics import f1_score, precision_score, recall_score
    f1 = f1_score(file_preds[label_col], file_preds['tx_pred'])
    precision = precision_score(file_preds[label_col], file_preds['tx_pred'])
    recall = recall_score(file_preds[label_col], file_preds['tx_pred'])
    
    return f1, precision, recall, file_preds

# OOF с группировкой по файлам (чтобы не было leakage)
def oof_mil(df, create_model_fn, file_id_col='file_id', n_splits=5):
    skf = GroupKFold(n_splits=n_splits)
    oof_proba = np.zeros(len(df))
    
    for train_idx, val_idx in skf.split(df, df['label'], groups=df[file_id_col]):
        train = df.iloc[train_idx]
        val = df.iloc[val_idx]
        
        # Обучение на транзакциях
        model = create_model_fn()
        model.fit(train['text'], train['label'])
        
        # Предсказания на валидации
        oof_proba[val_idx] = model.predict_proba(val['text'])[:, 1]
    
    return oof_proba
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 32. Почему в Security часто `β<1`, а в Медицине `β>1`? Влияние стоимости FP/FN

**Кратко:** `β` — это переводчик бизнес-требований на язык метрик. В Security `β<1` (Precision важнее), в Медицине `β>1` (Recall важнее), потому что стоимость ошибок разная.

**Подробно:**
|Домен|Приоритет|Типичный β|Почему|
|-----|---------|----------|-------|
|**Кибербезопасность**|Precision|`0.3-0.7`|FP = alert fatigue, простой бизнеса, лишние часы аналитиков. Лучше пропустить 10 атак, чем заблокировать легитимный трафик банка.|
|**Медицина**|Recall|`1.5-3.0`|FN = пропущенный рак/инсульт = жизнь/смерть. Ложноположительный → доп. анализы, что дорого, но не критично.|
|**Фрод/Платежи**|Баланс/Recall|`1.0-2.0`|FN = прямой финансовый ущерб. Точнее ловить мошенника, чем блокировать честного клиента (последнее компенсируется поддержкой).|

**Как это влияет на порог:**
- `β<1` → оптимизатор сдвигает порог **вверх** (требует больше уверенности для `1`)
- `β>1` → порог **вниз** (лучше перестраховаться)

**Математическая связь с бизнес-стоимостью:**  
Минимизация `E[Cost] = FP·C_FP + FN·C_FN` эквивалентна оптимизации `Fβ` при `β = √(C_FP / C_FN)`.  
В Security обычно `C_FP ≪ C_FN`, но из-за масштабирования алертов `C_FP` быстро растёт → выбирают умеренный `β≈0.5`.

**DevOps-контекст:** На собеседовании всегда начинайте с: _«Сначала определим стоимость ошибки, потом выберем β»_. В продакшене логируйте `C_FP` и `C_FN` как бизнес-метрики для пересмотра `β` при изменении контекста.

**Команды:**
```python
# Расчёт β из бизнес-стоимостей
def beta_from_costs(cost_fp, cost_fn):
    """Вычислить β для минимизации ожидаемой стоимости"""
    return np.sqrt(cost_fp / cost_fn)

# Пример: Security
cost_fp_security = 10    # $10 за ложный алерт (время аналитика)
cost_fn_security = 1000  # $1000 за пропущенную атаку (потенциальный ущерб)
beta_security = beta_from_costs(cost_fp_security, cost_fn_security)
print(f"Optimal β for Security: {beta_security:.2f}")  # ~0.1 → но на практике берут 0.5 из-за масштабирования

# Пример: Медицина
cost_fp_med = 100      # $100 за дополнительный анализ
cost_fn_med = 100000   # $100k за пропущенный диагноз
beta_med = beta_from_costs(cost_fp_med, cost_fn_med)
print(f"Optimal β for Medicine: {beta_med:.2f}")  # ~31.6 → на практике 2-3 из-за ограничений

# Оптимизация порога с учётом β
def find_threshold_for_cost(y_true, y_proba, cost_fp, cost_fn):
    """Найти порог, минимизирующий ожидаемую стоимость"""
    best_cost = np.inf
    best_thresh = 0.5
    
    for thresh in np.arange(0.1, 0.9, 0.01):
        preds = (y_proba >= thresh).astype(int)
        fp = np.sum((preds == 1) & (y_true == 0))
        fn = np.sum((preds == 0) & (y_true == 1))
        cost = fp * cost_fp + fn * cost_fn
        
        if cost < best_cost:
            best_cost = cost
            best_thresh = thresh
    
    return best_thresh, best_cost

# Использование
threshold, min_cost = find_threshold_for_cost(y_val, y_proba_val, cost_fp_security, cost_fn_security)
print(f"Optimal threshold: {threshold:.4f}, Expected cost: ${min_cost:.2f}")
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 33. Как бороться с Concept Drift в кибербезопасности?

**Кратко:** В Security модель «живёт» 3-6 месяцев. Без MLOps-пайплайна (непрерывное обучение, мониторинг дрейфа, active learning) она превращается в legacy-сигнатуру.

**Подробно:**
|Тип дрейфа|Что меняется|Пример в Security|Стратегия борьбы|
|----------|-----------|----------------|---------------|
|**Covariate shift**|P(X) | Новые протоколы, TLS 1.3, IPv6, CDN-маскировка|Мониторинг признаков (PSI), адаптивные фичи|
|**Prior shift**|P(Y) | Всплеск кампаний (Log4Shell) → доля malware растёт|Адаптивные пороги, мониторинг доли предсказаний|
|**Concept shift**|P(Y\|X) | Новые DGA-алгоритмы, обфускация, C2-структура|Active learning, непрерывное переобучение, гибридные системы|

**Детекция дрейфа:**
- `PSI (Population Stability Index)` для категориальных/бинированных признаков. `PSI > 0.2` → сильный дрейф.
- `KS-test` / `Wasserstein distance` для непрерывных (энтропия, длина, `chi_sq`).
- Мониторинг распределения `model confidence`: сдвиг медианы или рост дисперсии = модель «плавает».
- Отслеживание `FP-rate` по фидбеку аналитиков.

**Стратегии борьбы:**
1. **Active Learning:** Помечать только самые неопределённые предсказания (`0.4 < proba < 0.6`). Экономит разметку, быстро адаптирует модель.
2. **Continuous Retraining Pipeline:** Автоматический сбор новых данных → валидация → переобучение → A/B тест → деплой (цикл 2-4 недели).
3. **Ensemble of Experts:** ML + правила (Suricata, YARA) + Threat Intelligence feeds. Если ML деградирует, правила страхуют.
4. **Drift-robust features:** Использовать поведенческие/статистические признаки (энтропия, частота запросов, время жизни сессии) вместо статических строк.
5. **Adaptive Thresholds:** Динамически менять порог в зависимости от текущей `prior probability` и нагрузки на SOC.

**DevOps-контекст:** В пайплайнах всегда добавляйте шаг валидации на свежих размеченных данных перед деплоем новой версии модели. Если `F1` упал >5% — откатывайтесь и исследуйте причину.

**Команды:**
```python
# Мониторинг дрейфа признаков
def monitor_drift(train_df, test_df, feature_cols, psi_threshold=0.2):
    """Вернуть признаки с сильным дрейфом"""
    drifted = []
    for col in feature_cols:
        if train_df[col].dtype in ['float64', 'float32', 'int64']:
            # KS-test для непрерывных
            from scipy.stats import ks_2samp
            stat, p = ks_2samp(train_df[col].dropna(), test_df[col].dropna())
            if p < 0.05:
                drifted.append((col, f'KS p={p:.4f}'))
        else:
            # PSI для категориальных
            psi = calculate_psi(train_df[col], test_df[col])
            if psi > psi_threshold:
                drifted.append((col, f'PSI={psi:.3f}'))
    return drifted

# Active learning: выбор самых неопределённых для разметки
def select_uncertain_samples(X_unlabeled, model, n_select=100, strategy='margin'):
    """Выбрать образцы для активной разметки"""
    proba = model.predict_proba(X_unlabeled)[:, 1]
    
    if strategy == 'margin':
        # Минимальный отрыв от 0.5
        uncertainty = 1 - np.abs(proba - 0.5) * 2
    elif strategy == 'entropy':
        # Максимальная энтропия
        uncertainty = -proba * np.log2(proba + 1e-10) - (1-proba) * np.log2(1-proba + 1e-10)
    
    top_idx = np.argsort(uncertainty)[-n_select:]
    return X_unlabeled.iloc[top_idx], proba[top_idx]

# Адаптивный порог на основе prior probability
def adaptive_threshold(base_threshold, prior_shift, sensitivity=0.5):
    """Сдвиг порога в зависимости от изменения доли позитивов"""
    # Если prior растёт (больше атак) → снизить порог для сохранения Recall
    # Если prior падает → поднять порог для защиты Precision
    adjusted = base_threshold - sensitivity * prior_shift
    return np.clip(adjusted, 0.1, 0.9)
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 34. Опасность TF-IDF для обфусцированных/зашифрованных нагрузок + альтернативы

**Кратко:** Обфускация ломает синтаксис, но оставляет статистический «шум» и поведенческий паттерн. Ловите не строки, а **интент и аномалии**.

**Подробно:**
- **Проблема TF-IDF:**
  - Работает на **точных совпадениях токенов**. Обфускация (`base64`, `\x41`, конкатенация строк, переменные) полностью ломает токенизацию.
  - Высокая размерность → 99% нулей → модель учится на шумных n-граммах, не обобщает.
  - Не понимает **семантику**: `exec`, `execute`, `RunShell` для TF-IDF — разные вселенные.

- **Альтернативы для контекста:**
|Метод|Что даёт|Когда применять|
|-----|--------|--------------|
|**Char-level n-grams / HashingVectorizer**|Устойчив к мутациям, не требует словаря|Быстрый baseline, логи с обфускацией|
|**FastText / Subword Embeddings**|Учитывает морфологию, работает с OOV|Команды, скрипты, короткие строки|
|**AST / Control Flow Graphs**|Структура кода, игнорирует имена переменных|Статический анализ бинарников/скриптов|
|**LLM Embeddings (CodeBERT, StarCoder)**|Семантика, интент, контекст вызовов|Глубокий анализ, богатые ресурсы|
|**Behavioral Features**|Syscalls, network flows, file ops|Динамический анализ, песочницы|
|**Graph NN / Call Graphs**|Взаимосвязи модулей, пути выполнения|Продвинутая детекция APT, lateral movement|

**Практический совет:** В продакшене часто используют **гибрид**: `TF-IDF (быстро) + Entropy/Stats (устойчиво) + Rule Engine (YARA/Suricata)`. Если нагрузка зашифрована (TLS, custom crypto), TF-IDF бесполезен → переходим к мета-признакам потока (время, размер, направление, JA3-хеш).

**DevOps-контекст:** В пайплайнах детекции добавляйте шаг «fallback»: если TF-IDF-модель неуверенна (`0.4 < proba < 0.6`), передавайте на правило-движок или LLM-анализ.

**Команды:**
```python
# Гибридный пайплайн: TF-IDF + статистики + правила
def hybrid_predict(text, tfidf_model, clf, rule_engine, threshold=0.5):
    """Комбинированное предсказание"""
    # 1. Основной прогноз через TF-IDF + ML
    X_vec = tfidf_model.transform([text])
    ml_proba = clf.predict_proba(X_vec)[0][1]
    
    # 2. Если неуверенно → правило-движок
    if 0.4 < ml_proba < 0.6:
        rule_score = rule_engine.evaluate(text)  # YARA/Suricata
        if rule_score > 0.7:
            return 1, f"ML:{ml_proba:.2f}+Rule:{rule_score:.2f}"
    
    # 3. Статистические фичи как резерв
    entropy = calculate_entropy(text)
    if entropy > 4.0:  # Высокая энтропия = возможный DGA/обфускация
        ml_proba = min(ml_proba * 1.2, 1.0)  # Усилить уверенность
    
    return (ml_proba >= threshold).astype(int), f"ML:{ml_proba:.2f}"

# Fallback на LLM-эмбеддинги для сложных случаев
from transformers import AutoTokenizer, AutoModel
import torch

def get_code_embedding(text, model_name='microsoft/codebert-base'):
    """Получить эмбеддинг через CodeBERT для семантического анализа"""
    tokenizer = AutoTokenizer.from_pretrained(model_name)
    model = AutoModel.from_pretrained(model_name)
    
    inputs = tokenizer(text, return_tensors='pt', truncation=True, max_length=512)
    with torch.no_grad():
        outputs = model(**inputs)
    
    # Mean pooling
    embedding = outputs.last_hidden_state.mean(dim=1).squeeze().numpy()
    return embedding

# Использование: если ML неуверен, получить эмбеддинг и сравнить с базой известных атак
def semantic_similarity(text, known_attack_embeddings, threshold=0.8):
    embedding = get_code_embedding(text)
    similarities = [cosine_similarity([embedding], [emb])[0][0] 
                   for emb in known_attack_embeddings]
    return max(similarities) > threshold
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]

---

## 35. Мониторинг модели после деплоя в SOC/SIEM. Метрики и реакция на деградацию

**Кратко:** Мониторинг ML ≠ мониторинг софта. Здесь **метаданные важнее метрик**: какие признаки изменились? как сместилась уверенность? есть ли фидбек аналитиков? Без этого модель слепнет за месяц.

**Подробно:**
**Архитектура мониторинга (4 слоя):**
1. **Data Layer:** Распределение признаков, `PSI`, `KS-test`, missing values rate.
2. **Model Layer:** `Confidence drift`, `FP/TP rate` (по фидбеку), `F1/Fβ` (при delayed labels), prediction latency.
3. **System Layer:** Throughput, CPU/GPU usage, OOM, error rates, queue depth.
4. **Business Layer:** Alert volume per analyst, mean time to triage (MTTT), false positive escalation rate.

**Как реагировать на деградацию:**
🔹 **Trigger:** `PSI > 0.15` ИЛИ `FP-rate вырос на 30%` ИЛИ `latency > SLA`.  
🔹 **Step 1:** Автоматический алерт в Slack/PagerDuty + дамп последних 10k предсказаний.  
🔹 **Step 2:** Rollback к предыдущей стабильной версии (если критично).  
🔹 **Step 3:** Diagnosis: это дрейф данных? Пайплайн сломался? Новая атака?  
🔹 **Step 4:** Retrain: собрать свежие размеченные данные → обучить → валидировать на hold-out + shadow mode.  
🔹 **Step 5:** Deploy via Canary (5% → 20% → 100%) + мониторинг бизнес-метрик.  
🔹 **Step 6:** Обновить monitoring thresholds и документацию.

**Интеграция с SIEM:**
- Предикты пишутся как события в Elastic/Splunk.
- Аналитики ставят теги `TP/FP/Unknown` → автоматическая обратная связь.
- Dashboard: Grafana + MLflow + Prometheus.

**DevOps-контекст:** В Security пайплайнах добавляйте шаг «shadow mode»: новая модель параллельно со старой, без влияния на алерты. Это позволяет безопасно валидировать на реальных данных.

**Команды:**
```python
# Мониторинг дашборд: ключевые метрики для логирования
def log_model_metrics(predictions, features, metadata):
    """Логировать метрики для мониторинга"""
    metrics = {
        # Data layer
        'feature_psi': calculate_psi_batch(features),
        'missing_rate': np.mean([np.isnan(f).mean() for f in features.values()]),
        
        # Model layer
        'confidence_mean': np.mean(predictions['proba']),
        'confidence_std': np.std(predictions['proba']),
        'prediction_rate': np.mean(predictions['pred']),  # доля алертов
        
        # System layer
        'latency_ms': metadata['inference_time_ms'],
        'memory_mb': metadata['memory_usage_mb'],
        
        # Business layer (если есть фидбек)
        'fp_rate_feedback': metadata.get('fp_rate', None),
        'analyst_triage_time': metadata.get('mttt_minutes', None),
    }
    
    # Отправка в Prometheus/Grafana
    for name, value in metrics.items():
        if value is not None:
            prometheus_metric(f'ml_model_{name}', value)
    
    return metrics

# Canary deployment для безопасного обновления
def canary_deploy(new_model, old_model, X_test, traffic_ratio=0.05):
    """Запустить новую модель на 5% трафика"""
    predictions = []
    
    for i, sample in enumerate(X_test):
        if np.random.random() < traffic_ratio:
            # Canary: новая модель
            pred = new_model.predict(sample)
            predictions.append(('canary', pred))
        else:
            # Control: старая модель
            pred = old_model.predict(sample)
            predictions.append(('control', pred))
    
    # Сравнение метрик между canary и control
    canary_preds = [p for tag, p in predictions if tag == 'canary']
    control_preds = [p for tag, p in predictions if tag == 'control']
    
    return {
        'canary_alert_rate': np.mean(canary_preds),
        'control_alert_rate': np.mean(control_preds),
        'delta': np.mean(canary_preds) - np.mean(control_preds)
    }

# Автоматический rollback при деградации
def auto_rollback_check(current_metrics, baseline_metrics, thresholds):
    """Проверить, нужен ли rollback"""
    for metric, threshold in thresholds.items():
        if metric in current_metrics and metric in baseline_metrics:
            delta = abs(current_metrics[metric] - baseline_metrics[metric])
            if delta > threshold:
                return True, f"Rollback: {metric} changed by {delta:.3f} > {threshold}"
    return False, "OK"
```

[[#📑 Оглавление для навигации|↑ К оглавлению]]