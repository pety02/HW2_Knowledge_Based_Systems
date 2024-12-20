# Системи основани на знание: **Домашна работа No 2**

## Условие на задачата:
Задачата, която трябва да се изпълние е създаване на **онтология с помощта на Protégé OWL (ver. 5.2)**. Целта при тази задача е да се състави онтология, която представя информация за дадено множество обекти по ваш избор (например книги, песни, мобилни телефони, автомобили и т.н.). Основната информация, която трябва да бъде моделирана, описвайки **класове**, **събития** и **свойства** за избраните от вас видове обекти е **от областта на информационните системи**. Също така трябва **да се опишат допускания**, като например, че има само една записана версия на всяка песен. Обектите могат да принадлежат към различни категории (поне две). Например, песните могат да принадлежат към различни жанрове, като "Рок" и "Поп". **Онтологията** ви **трябва да включва описания на поне 15 понятия (класове) и 10 свойства**, специфицирани както следва и реализиращи **йерархична структура**. Онтологията ви ще се счита за пълна, ако съдържа **консистентни описания на всички видове посочени класове** и **примери за категоризация**. За всеки клас трябва да са създадени **екземпляри (индивиди)**. Необходимо е да определите:
1. кои класове са взаимно чижди (**disjoint**);
2. подходящи характеристики на използваните свойства (**functional / inverse / symmetric / transitive**);
3. ограничения и(ли) дефиниционни области (**range / domain**) на свойствата, за които това е приложимо / подходящо. С **подходящи индивиди трябва да покажете, че вашата онтология може да се използва за моделиране и на други данни**. Необходимо е да използвате мнемонични имена на класовете, свойствата и индивидите, които дефинирате.

## Описание на предметната област:
Темата, към която се насочих при **решаването на тази задача е онтология, която да представя работата на един бар / заведение** като за целта реализирах Entity класове за бар, клиент, различните продукти в даден бар, държава (, в която може да се намира въпросното заведние или от която може да произхождат различни продукти, използвани за приготвянето на дадни артикули в бара). Също така посредством различни свойства (object или data) съм описала връзките между класовете и зъм задала условия, по които онтологията успешно да може да разпознава и класифицира на по-късен етап всеки новосъздаден индивид.

## Описание на класовете в онтологията и описание на йрархичния модел в онтологията: 
- **Bar** - характеризира се с това, че е **подклас на owl:Thing**, че се намира в определена държава и че предлага някакви продукти;
- **Client** - характеризира се с това, че е **подклас на owl:Thing**;
- **MenuItem** - характеризира се с това, че е **подклас на owl:Thing**, предлага се в даден бар, съдържа минимум 0 калории и струва минимум 1 лев;
- **Drink** - характеризира се с това, че е **подклас на MenuItem**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев и количеството й е минимум 200 ml; 
- **Alchoholic** - характеризира се с това, че е **подклас на Drink**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 200 ml и е алкохолна; 
- **Spirit** - характеризира се с това, че е **подклас на Alchoholic**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 200 ml и е алкохолна (наследява всичко от Alchoholic без промяна - онтологита тук би могла да се обогати с други отличителни качества на спиртните напитки);  

**Следващите 3 класа са просто примерни разновидности на спиртни алкохоли**:
- **Rum**
- **Vodka**
- **Whiskey**
- **Wine** - характеризира се с това, че е **подклас на Alchoholic**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml и е алкохолна (наследява всичко от Alchoholic без промяна - онтологита тук би могла да се обогати с вкусове, аромати и други отличителни качества на вината);   
- **Red** - характеризира се с това, че е **подклас на Wine** и описва червени вина; 
**Следващите 2 класа са просто примерни разновидности на червени вина**:
- **Cabernet-Souvignon**
- **Merlot**
- **Rose** - характеризира се с това, че е **подклас на Wine** и описва розета;    
**Следващите 2 класа са просто примерни разновидности на розета**:
- **Garnacha**
- **Pinot-Noir**    
- **White** - характеризира се с това, че е **подклас на Wine** и описва бели вина;    
**Следващите 2 класа са просто примерни разновидности на бели вина**:
- **Chardonnay**
- **Risling**       
- **Cocktail** - характеризира се с това, че е **подклас на Drink**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев и количеството му е минимум 200 ml (наследява всичко от Drink без промяна - онтологията тук би могла да се обогати с други отличителни качества на коктейлите - алкохолни или не);  
- **Alchoholic** - характеризира се с това, че е **подклас на Cocktail**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml, съдържа някакъв алкохол, сържа някаква безалкохолна напитка, сервира се с мезе и сам по себе си е алкохолен;  
- **Non-Alchoholic** - характеризира се с това, че е **подклас на Cocktail**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml, има минимум 2 безалкохоолни напитки и сам по себе си е безалкохолен;   
- **Non-Alchoholic** - характеризира се с това, че е **подклас на Drink**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml и е безалкохолна; 
- **Fizzy** - характеризира се с това, че е **подклас на Non-Alchoholic**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml, безалкохолна е и е газирана;   
- **Hot** - характеризира се с това, че е **подклас на Non-Alchoholic**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml и се сервира на минимум 60 градуса;           
- **Coffee** - характеризира се с това, че е **подклас на Hot**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml, сервира се на минимум 60 градуса и е овкусена с някаква разновидност кафяна напитка;
- **Tea** - характеризира се с това, че е **подклас на Hot**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството му е минимум 200 ml, сервира се на минимум 60 градуса и е овкусена с някакви плодове;
- **Juice** - характеризира се с това, че е **подклас на Non-Alchoholic**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев и количеството му е минимум 200 ml (наследява всичко от Non-Alchoholic без промяна - онтологията тук би могла да се обогати от други отличителни качества на соковете);  
- **Water** - характеризира се с това, че е **подклас на Non-Alchoholic**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев и количеството му е минимум 200 ml (наследява всичко от Non-Alchoholic без промяна - онтологията тук би могла да се обогати от други отличителни качества на водата);       
- **Food** - характеризира се с това, че е **подклас на MenuItem**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев и количеството й е минимум 170 грама; 
- **Appetaizers** - характеризира се с това, че е **подклас на Food**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 170 грама, сервира се с алкохолна напитка или алкохолен коктейл (като първо се сервира напитката);    
- **Salad** - характеризира се с това, че е **подклас на Appetizers**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 170 грама, сервира се с алкохолна напитка или алкохолен коктейл (като първо се сервира напитката) и съставките й са някакви зеленчуци;
- **Fruits** - характеризира се с това, че е **подклас на Food**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев и количеството й е минимум 170 грама (наследява всичко от Food без промяна - онтологията тук би могла да се обогати от други отличителни качества на плодовете);   
- **Starters** - характеризира се с това, че е **подклас на Food**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 170 грама и се сервират след мезетата;    
- **Sweets** - характеризира се с това, че е **подклас на Food**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 170 грама и се сервират след стартерите;    
- **Vegetables** - характеризира се с това, че е **подклас на Food**, предлага се в даден бар, съдържа минимум 0 калории, струва минимум 1 лев, количеството й е минимум 170 грама и се сервират след салатите;    
- **Country** - характеризира се с това, че е **подклас на owl:Thing**;

## Описание на object свойстата в онтологията:
- **hasBar** - описва връзката между държавите и баровете като се има предвид, че в една сържава могат да се съдържат много барове;
    - **domain** - Country; 
    - **range** - Bar;
- **hasClient** - описва връзката между баровете и клиентите като се има предвис, че един бара може да има множество клиенти, **inverse property** на isClientOf;
    - **domain** - Bar; 
    - **range** - Client;
- **hasIngridient** - описва връзката между артикул на даден бар и съставки, които могат да са артикули на същия бар или на друг такъв, **inverse property** на isIngridientOf;
    - **domain** - MenuItem; 
    - **range** - MenuItem;
- **isClientOf** - описва връзката между клиентите и баровете като се има предвид, че един човек може да е клиент на нула, един или повече барове, **inverse property** на hasClient;
    - **domain** - Client; 
    - **range** - Bar;
- **isFlavoredWith** - описва връзката между различни продукти / артикули на барове като се има предвид, че даден артикул може да има вкуса на друг продук / артикул, тоест да бъде овкусен от различни продукти;
    - **domain** - MenuItem; 
    - **range** - MenuItem;
- **isHomelandOf** - описва връзката между артикул на даден бар и неговата родина (държава) като се има предвид, че един артикул може да произлиза от дадена страна, **inverse property** на originateFrom;
    - **domain** - Country; 
    - **range** - MenuItem;
- **isIngridientOf** - описва връзката между различни продукти като се иам предвид, че един продукт може да е съставка на друг такъв, **inverse property** на hasIngridient;
    - **domain** - MenuItem; 
    - **range** - MenuItem;
- **isOfferedIn** - описва връзката между продуктите и баровете като се има предвид, че даде продулт се предлага в даден бар, **inverse property** на offers;
    - **domain** - MenuItem; 
    - **range** - Bar;
- **isServedAfter** - описва връзката между ястията в баровете (кое след кое се сервира), **inverse property** на isServedBefore;
    - **domain** - MenuItem; 
    - **range** - MenuItem;
- **isServedBefore** - описва връзката между ястията в баровете (кое кое предшества), **inverse property** на isServedAfter;
    - **domain** - MenuItem; 
    - **range** - MenuItem;
- **isSituatedIn** - описва връзката между баровете и държавите (кой бар къде се намира), **inverse property** на hasBar;
    - **domain** - Bar; 
    - **range** - Country;
- **offers** - описва връската между баровете и артикулите, които предлагат, **inverse property** на isServedIn;
    - **domain** - Bar; 
    - **range** - MenuItem;
- **orignateFrom** - описва връзката между артикулите на баровете и държавите (кой продукт / артикул от коя страна произхожда), **inverse property** на isHomelandOf;
    - **domain** - MenuItem; 
    - **range** - Country;
- **producedIn** - описва връзката между артикулите и баровете (кой продукт / артикул в кой бар се произвежда);
    - **domain** - MenuItem; 
    - **range** - Bar;
- **servedWithDrink** - описва връзката между артикулите в баровете (коя храна с коя напитка се сервира), **inverse property** на servedWithFood;
    - **domain** - Food; 
    - **range** - Drink;
- **servedWithFood** - описва връзката между артикулите в баровете (коя напитка с коя храна се сервира), **inverse property** на servedWithDrink;
    - **domain** - Drink; 
    - **range** - Food;

## Описание на data свойствата в онтологията:
- **containsCalories** - указва броя калории в даден артикул;
- **isAlchoholic** - указва дали дадена напитка е алкохолна или не;
- **hasAlchoholicContent** - указва съдържанието на алкохол на дадена напитка;
- **hasPrice** - указва цената на даден артикул;
- **hasServingSize** - указва големината на порцията на даден артикул;
- **isCarboanted** - указва дали дадена напитка е газирана или не;
- **servedAtTemperature** - указва температурата, на която се сервира дадена напитка;

## Описание на събитията в онтологията:
Посредством **класа Client** и двете **object property-та**: **isClientOf** и **hasClient** съм моделирала **действието на имане на клиенти и това да бъдеш клиент на дадено заведение**, тоест начина, по който функционират заведенията. 

## Примерни резултати с пояснения:
Може да разгледате примерните визуализации на онтологията, заедно с коментари към тях в документацията на домашното.

## Реализацита на онтологията като owl код:
**Може да клонирате GitHub repository-то на проекта** чрез следната команда в терминала.
```bash
    git clone https://github.com/pety02/HW2_Knowledge_Based_Systems.git
```
Ако не желате да клонирате repository-то на проекта, **може да разгледате предоставения по-долу изходен код**.
Разгледайте **Drinks.owx** файла. 
