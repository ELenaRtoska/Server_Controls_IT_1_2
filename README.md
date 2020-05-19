# Server_Controls_IT_1_2

## Серверски контроли 1
1. Отворете VisualStudio.    

2. Креирајте нов веб сајт кој ќе биде сместен на локалниот податочен систем со програмски код во програмскиот јазик C#.    

3. Од менито ToolBox извлечете контрола од типот Label и  поставете ја во дизајнерскиот прозорец на страницата Default.aspx    

4. Селектирајте ја компонентата и преку менито Properties поставете ги следните својства:      

    Име: lblVreme1  

    Фонт: Arial  
    
    Боја на текст. Navy   
    
    Големина: Medium  
    
    Текст: “Kонтрола за приказ на време”  
  
5. Извршете ја апликацијата (бидејќи сајтот се компајлира за прв пат, ќе се појави прозорец кој ќе ве праша дали сакате да се компајлира сајтот со дебагирање. Одоговорете потврдно)    

6. Откако ќе го добиете резултатот, прекинете го компајлирањето.    

7. Во датотеката Default.aspx.cs испрограмирајте го настанот Page_Load, така што ќе се прикаже времето:   lblVreme1.Text = DateTime.Now.ToString();  
  
8. Извршете ја апликацијата, а потоа неколку пати освежете ја страницата. Што забележувате? 
 
-Се прикажува моменталното времето наместо предефинираната вредност за тект. 
 
9. Од менито ToolBox извлечете контроли од типот Label и Button и  поставете ги во дизајнерскиот прозорец на страницата Default.aspx. Именувајте ги како lblVreme2 и btnVreme, соодветно и додадете им ги истите својства како и на компонентата lblVreme1.  
Интернет Технологии  
  
    
10. Селектирајте ја компонентата btnVreme1, и во подменито Events од менито Properties, изберете го настанот Click, и двојно кликнете во празното поле, десно од името на настанот.    

11. Испрограмирајте го настанот Click на копчето btnVreme, така што lblVreme2 ќе го прикаже моменталното време во моментот кога ќе се клинке на копчето.    

12. Како се одразува промената на својствата и настаните на компонентата во .aspx кодот?  
 
-На почеток кога се уклучува апликацијата во првата лабела го пишува времето кога е стартувана апликацијата, додека пак кога ќе се кликне копчето настанува промена во двете лабели т.ш сега во двете се прикажува времето кога се кликнало копчето.  
  
13. Кодот во  Page_Load заменете го со:   if (!Page.IsPostBack)  
                lblVreme1.Text = DateTime.Now.ToString();   
  
14. Извршете ја апликацијата, и кликнете неколку пати на копчето. Разгледајте го поведението на апликацијата.   -Сега, кога ќе се кликне копчето нема влијание на првата лабела.   

15. Прекинете ја апликацијата.    

16. Вметнете точки на прекин (Break Points) кај првата наредба од Page_Load и btnVreme_Click, и обидете се да го објасните значењето на својството IsPostBack на објектот Page.  
 
-Својството IsPostBack на објектот Page е во тоа што враќа true/false во зависност од тоа дали имаме нешто вратено преку browser. Доколку е false тогаш не би имало некаква интеракција на одредено место кога ќе се предизвика некој настан. 
  
17. Kреирајте нова страница со име Default2.aspx    

18. На страницата Default1.aspx внесете контрола од типот HiperLink.    

19. Именувајте ја како hlSledno и во својството NavigateUrl изберете ја како локација, штотуку креираната страница Default2.aspx.    
Интернет Технологии  
  
20. Во страницата Default2.aspx внесете табела (Layot->Table) и преку изворниот приказ на дизајнерскиот прозорец, центрирајте ја табелата во средина на страницата:  <table align=center>  
  
21. Во табелата внесете компонента pnlPanela1 од типот Panel и променете и го предефинираниот фонт и позадинска боја.    

22. Во компонентата pnlPanela1 внесете две компоненти од типот ТеxtBox со име txtOperand1 и txtOperand2 и по една од типот Label и Button со имиња lblRezultat и btnSoberi, соодветно.    

23. Испрограмирајте го копчето btnSoberi  со следниот код:   
``` 
int op1 = Convert.ToInt32(txtOperand1.Text);          int op2 = Convert.ToInt32(txtOperand2.Text);    
         lblRezultat.Text = Convert.ToString(op1 + op2);  
```  
24. Извршете ја апликацијата.    

25. За да следното извршување, апликацијата првично ја прикаже страницата Default2.aspx, наместо Default.aspx, во Solution Explorer, лоцирајте ја страницата Default.aspx и со десен клик врз нејзиното име, изберете ја ставката Set as Start Page од менито кое се појавува.    

26. Во табелата, надвор од pnlPanela, внесете компонента од типот CheckBox. Именувајте ја како chbVidlivo и на својството Text доделете му вредност “Видливо”.    

27. Двојно кликнете врз chbVidlivo и внесете го следниот код:    
 
if (chbVidlivo.Checked)  
               pnlPanela.Visible = true;  
        else      
                 pnlPanela.Visible=false;     

28. Извршете ја апликацијата. Дали апликацијата го има очекуваното поведение?  -Не, затоа што AutoPostBack својството на chbVidlivo е по диголт false, а ние не го променивме. 
 
Интернет Технологии  
  
29. Поставете го својството AutoPostBack на chbVidlivo на вредност true, и повторно извршете ја апликацијата.    

30. Поставете го својството AutoPostBack на txtOperand2 на вредност true, двојно кликнете врз компонентата и во изворнито код внесете го кодот од точка 24. Повторно извршете ја апликацијата.    

31. Кое е значењето на својството AutoPostBack?  - AutoPostBack е механизам со кој страницата ќе биде испратена назад кон серверот автоматски, врз основа на некои настани во веб-контролите. Во некои од веб-контролите ако AutoPostBack е true - ќе се испрати барањето до серверот кога ќе се случи некој настан во контролата. 
 
32. Променете го својството EnableViewState  на компонентите txtOperand1 и lblRezultat на вредност false.    

33. Извршете ја апликацијата, внесете целобројни вредности во текстуалните полиња и неколку пати променете ја селекцијата на chbVidlivo.    

34. Кое е значењето на својството EnableViewState?  - Својството EnableViewState и овозможува на страницата да ги зачува податоците кои се внесени од корисникот. Ги зачувува податоците на страна на серверот во ViewState, што се зачувува како скриена вредност на страницата пред страницата да биде испратена на клиентите преку browser.     

35. Креирајте страница со име Default3.aspx.    

36. Внесете 2 компоненти од типот TextBox со име txtLozinka и txtPoraka, две компоненти од типот Button со име btnProveri и btnPrvaStrana, од кои последната треба да има својство Enabled поставено на вредност false.    

37. Поставете го својството TextMode на txtLozinka на вредност Password, а на txtPoraka на вредност MultiLine при што ќе бидат прикажани 5 линии. Поставете го својството ReadOnly на вредност True.    

38. Испрограмирајте го настанот Click на копјето btnProveri така што корисникот ќе може да внесе текст во txtPoraka само ако лозинката има вредност “мрежно програмирање”. Ако лозинките 
Интернет Технологии  
  
  
се совпаѓаат, потребно е да се постави фокусот во компонентата txtPoraka. Ако лозинките не се совпаѓаат, потребно е да се испише порака за грешка без користење на веб компоненти.  
  
39. Испрограмирајте ја компонентата txtPoraka така што кога  истата ќе се напушти, ќе се овозможи употреба на копчето btnPrvaStrana.    

40. Копчето btnPrvaStrana да се испрограмира така што кога ќе се притисне, ќе го пренасочи корисникот на страницата Default.aspx.  
