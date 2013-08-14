<h1>מסמך תיעוד – CRAZY CAT LADY</h1>
<h2>מטרת הפרויקט:<h2>
<p>ליצור אפליקציית רשת בסביבת ASP.NET שתכיל מידע שימושי על גזעים שונים של חתולים. המידע ניתן שצפייה, שינוי והוספה.</p>
<h3>המידע המוצג:</h3>
<p>Cat breed, country, origin, body type, coat, pattern, information, image</p>
<p>וכמו כן קיים גם מידע על מוצרים לחתולים כגון: אוכל יבש, אוכל רטוב, צעצועים, פינוקים וויטמינים.</p>
<h3>טכנולוגיות בשימוש:</h3>
<p><b>שפות:</b></p>
* HTML, CSS – לעיצוב דפי האינטרנט.
* C# - לוגיקת התוכנה.
* SQL – התעסקות עם מסד הנתונים.
* Java script – לפתיחת חלונות הודעה.
*כאמור, סביבת העבודה היא Asp.net  framework ב visual studio 2012 וכל כל עמודי האפליקציה הם .aspx ולוגיקת העמודים עצמם - .aspx.cs
* מסד הנתונים נוצר ב – sql server 2012 בשפת sql.
<p><b>דרישות מערכת למשתמש:</b><p>
* כל מכשיר אלקטרוני שיש עליו דפדפן אינטרנט, כרטיס רשת תקין וחיבור לאינטרנט.
<p><b>דרישות למפתח:</b><p>
* Visual studio התומך בכתיבת אפליקציית רשת ב Asp.net framework 4.5
* שרת sql המכיל את הטבלאות של האפליקציה.
* במקרה הצורך אני יכול לפתוח גישה לחיבור מרחוק למסד הנתונים ואז אין צורך בהתקנת שרת sql מקומי, אלא רק לקבל ממני את נתוני ההתחברות.
* את קבצי המקור ניתן להוריד מהקישור הבא:
 https://github.com/kakifish/Crazy-Cat-Lady/tree/master/Cats%20Source%20Code/Cats

<h3>מבנה מסד הנתונים:</h3>
<p><b>במסד הנתונים ישנן ארבע טבלאות:</b></p>
<p><b>1. Cats – טבלה זו מכילה את השדות:</b></p>
*	Breed (מפתח ראשי).
*	Country.
*	Origin.
*	Body Type.
*	Coat.
*	Pattern.
*	Image.
*	Information.
<p>וכמובן שומרת את כל גזעי החתולים ואת מאפייניהם.</p>
<p><b>2. CatsAdmin – טבלה זו מכילה את השדות שישנם ב Cats ובנוסף את השדה:</b></p>
*	Changes.
<p>טבלה זו נועדה לשמור את השינויים שנעשו על ידי המשתמשים הרגילים וכמו כן מחיקת גזע חתול על-ידי עורך (ניתן לקרוא על סוגי משתמשים בהרחבה בהמשך), כאשר בשדה האחרון נשמר סוג השינוי (כגון מחיקת גזע חתולים, הוספת גזע חתולים וכו').</p>
<p><b>3. Products – טבלה זו מכילה את השדות הבאים:</b></p>
*	Category – (Dry Food, Wet Food, Toys, Treats, Vitamins).
*	Product Name.
*	Image.
*	Description.
*	Price.
*	Brand – נועד לסוגי אוכל.
*	Weight – נועד לאוכל יבש.
<p>אופציונאלי בעתיד (לפרסום חנויות):</p>
*	Store Name.
*	Store Address.
*	Store Phone.
<p>טבלה זו שומרת נתונים על מוצרים שונים לחתולים.</p>
<p><b>4.	Editors – מכילה את השדות הבאים:</b></p>
*	First Name.
*	Last name.
*	Username.
*	Password.
*	email.
*	Authorized.
<p>טבלה זו שומרת את נתוני העורכים הקיימים במערכת.
השדה Authorized משמש כדגל – כאשר השדה מכיל את הערך 0, העורך עדיין לא אושר על-ידי האדמיניסטראטור לגשת לעמודי העורכים.
כאשר השדה מכיל את הערך 1, העורך אושר ויכול להשתמש בפיצ'רים של העורכים.</p>

<p>-	כל השדות מקבלים string מלבד Authorized המקבל int.</p>

<h3>סוגי משתמשים:</h3>
<p><b>אדמיניסטראטור: ולדימיר נוביקוב. בעל הרשאות עורך (הסבר בהמשך), מאשר עורכים חדשים ומקבל עדכונים על שינויים קריטיים במייל במטרה לגבות נתונים.</b></p>
<p><b>משתמש רגיל: כל אדם יכול לגשת מבלי סיסמה ושם משתמש לתכני המידע שהאתר מספק. משתמש רגיל יכול לערוך את המידע הבא:</b></p>
*	לשנות אינפורמציה על החתול (.(information
*	לשנות מאפייני חתול (breed, country, origin, body type, coat, pattern, image).
*	להוסיף חתול.
<p>השינויים לא מועברים ישר לטבלה Cats אשר כל המשתמשים רואים את הנתונים שבה, אלא מועברים לטבלה CatsAdmin ורק העורכים יכולים לצפות בשינויים אלו ולהחליט אם לאשר או לא לאשר את השינויים הללו.</p>
<p>העמודים הם:<p>
* Home – מכיל הסבר קצר על התוכנה, תכניה ואופן השימוש.
* List Of All Cat Breeds – מכיל טבלה שבה יש את כל גזעי החתולים ומאפייניהם.
* Search For Cat Breed – ניתן לחפש גזע ע"י הזנת נתונים או למצוא את מאפייני הגזע ע"י הזנת שם הגזע.
בעמוד זה ניתן גם לערוך את האינפורמציה על הגזע.
* Add Cat – ניתן להוסיף גזע חתול חדש.
* Add/Change Cat Specifications – ניתן לשנות מאפייני גזע חתולים.
* Products – המכיל:
*	Dry Food – מכיל טבלה עם כל המידע על האוכל היבש שנמצא במסד הנתונים.
*	Wet Food – מכיל טבלה עם כל המידע על האוכל הרטוב שנמצא במסד הנתונים.
*	Toys – מכיל טבלה עם כל המידע על הצעצועים שנמצאים במסד הנתונים.
*	Treats – מכיל טבלה עם כל המידע על הפינוקים שנמצאים במסד הנתונים.
*	Vitamins – מכיל טבלה עם כל המידע על הויטמינים שנמצאים במסד הנתונים.
* Editor Login – מעמוד זה ניתן לגשת תעמוד ההרשמה של עורך או להיכנס כעורך. במידה ולא ניתנו הרשאות לעורך, תצא הודעת שגיאה האומרת כי עדיין לא התקבל אישור.
* Register As Editor – בעמוד זה עורך מזין את כל הפרטים הנדרשים. לאחר לחיצה על כפתור אישור, תצא הודעה שהפרטים נשלחו במייל לאדמיניסטראטור והבקשה מחכה לאישור, בינתיים ניתן לגלוש באתר כמשתמש רגיל.
<p><b>עורך (EDITOR):</b></p> 
אדם אשר קיבל הרשאות לבצע שינויים בטבלאות מסד הנתונים.
לאחר רגיסטרציית עורך חדש, האדמיניסטראטור מקבל מייל עם השם, שם משפחה ואי-מייל של אדם שרוצה להיות עורך. לאחר ראיון מקיף של האדמיניסטראטור עם אותו האדם במטרה לוודא שאין לנרשם כוונות זדוניות ויש לו הבנה עמוקה בנושא חתולים, האדמיניסטראטור מחליט עם לתת לעורך הרשאות או לא. שינוי הדגל של ההרשאה נעשה ישירות דרך מסד הנתונים בעזרת כלי מתאים (כגון STUDIO SQL SERVER MANAGEMENT).
לאחר קבלת ההרשאות
*	כל עמודי המשתמש הרגיל מופיעים אצל העורך אך כאשר עורך מבצע שינויים, השינויים נרשמים ישירות בטבלה Cats ולא עוברים ולידציה.
*	עמוד הבית של העורך משתנה ומופיעים בו הסברים על אופן השימוש בעמודי העורך.
*	מתווספים לעורך שלושה עמודים נוספים:
*	Changes – בעמוד זה מופיעה טבלה עם כל השינויים שבוצעו על ידי המשתמשים הרגילים ובנוסף גזעים של חתולים שנמחקו ע"י עורך.
הטבלה מכילה את הגזע ששונה ביחד עם המאפיינים, השינוי שבוצע ושני כפתורים – Confirm ו- Discard.
במידה ומדובר בשינוי ולא במחיקה, לחיצה על Confirm תכניס את השינויים לטבלה Cats, ולחיצה על Discard לא תבצע שינוי.
במידה ומדובר במחיקה, לחיצה על Confirm תמחק לצמיתות את הגזע, ולחיצה על Discard, תחזיר את הגזע חזרה לטבלה Cats.
*	Delete Breed – בעמוד זה יש טבלה של כל הגזעים עם המאפיינים וכמו כן ניתן לבחור מתוך רשימה גזע למחיקה. לחיצה על כפתור מחיקה תגרור שליחת מייל לאדמיניסטראטור עם הודעה שמכילה את מאפייני הגזע לצורך גיבוי וכמו כן הנתונים עוברים לטבלה CatsAdmin וניתן לצפות בהם בעמוד Changes ולשחזר משם.
*	Back To Regular User – לחזור חזרה לעמודי המשתמש הרגיש, ללא הרשאות עורך.

<h3>הרחבות נוספות:</h3>
*	בעמוד Search For Cat Breed ניתן לצפות באינפורמציה על הגזע ולערוך אותה.
מכיוון שאנו רוצים שהמידע על הגזע ייוצג באופן אסטטי ולא ב – TextBox בחרנו לכתוב את האינפורמציה ב Div עם תגיות HTML - <b>text</b> לטקסט מודגש, <i>text</i> לטקסט נטוי, <h1>text</h1> לכותרת מסוג 1, <h2>text</h2> לכותרת מסוג 2, <h3>text</h3> לכותרת מסוג 3.
<p>אופן העריכה בעמוד:<p>
עקב כך שהעברת התגיות ברשת פותחת בעיות אבטחה ולא רצינו לנטרל את ולידציית העמוד, בהשראת אופן העריכה הישן של ויקיפדיה ואתרים נוספים הוחלט לשנות את הסימונים ל – 
##B**text##/b** - לטקסט מודגש.
##i**text##/i** - לטקסט נטוי.
##h1**text##/h1** - לכותרת מסוג 1.
##h2**text##/h2** - לכותרת מסוג 2.
##h3**text##/h3** - לכותרת מסוג 3.
המידע שנשמר במסד הנתונים נשמר באופן הנ"ל ובעת השמתו ב DIV, המידע מפוענח לתגיות רגילות ומוצג באופן אסטטי.
תחילה נראה את האינפורמציה בעמוד ב DIV, עם הלחיצה על עריכה, הטקסט מועתק ל – TextBox לעריכה, ה- DIV נעלם ותיבת הטקסט מופיע ביחד עם הוראות כתיבה.
המשתמש יזין את השינויים כפי שהוא רוצה ולפי הסינטקס הנ"ל וילחץ על אישור.
לאחר מכן המידע יועבר למסד הנתונים ול – DIV על מנת שהמשתמש יראה כיצד השינויים שביצע יראו על המסך לאחר אישור עורך.
בשלב זה תיבת הטקט תוסתר ביחד עם ההוראות ויופע ה DIV עם הטקסט החדש במקומם.
*	קיים פרמטר admin המועבר מעמוד לעמוד בכדי להבדיל בין משתמש רגיל לעורך.
<p><b>הנחות:</b></p>
*	בעמודים בהם מוכנסים שינויים למסד נתונים, קיימת הנחה שמשתמש לא יבצע רענון לעמוד. בינתיים דבר זה גורם לשגיאה אך בעתיד נטפל בה. הדבר לא טופל עדיין עקב היקף הפרויקט וחוסר הזמן.
*	עמודי הבית של המשתמשים השונים עדיין לא מכילים מידע על התוכנה מהדבר נראה לנו פחות רלוונטי לפרויקט הזה.
*	עורך שמאושר על-ידי האדמיניסטראטור הוא אדם בעל אינטרס שהאתר יצליח ולא יגרום נזק לאתר.
