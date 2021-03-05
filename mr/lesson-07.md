---
layout: "lesson"
lang: "mr"
title: "दृश्यकांचा समावेश करणे व त्यांचे स्थान निश्चित करणे"
description: "ह्या प्रकरणात बाह्य दृश्यकांचा लाटेक्-दस्तऐवजात समावेश कसा करावा, त्यांचे रूप कसे बदलावे, त्यांना पृष्ठाच्या विशिष्ट स्थानावर कसे स्थापित करावे हे आपण शिकणार आहोत."
toc-anchor-text: "दृश्यकांचा समावेश"
toc-description: "दृश्यरूप, शब्दांमधील मोकळी जागा व स्थाननिश्चिती."
---

## दृश्यके व स्थाननिश्चिती

<span class="summary">
ह्या प्रकरणात बाह्य दृश्यकांचा लाटेक्-दस्तऐवजात समावेश कसा करावा, त्यांचे रूप कसे बदलावे, त्यांना
पृष्ठाच्या विशिष्ट स्थानावर कसे स्थापित करावे हे आपण शिकणार आहोत.
</span>

बाहेरील दृश्यके लाटेक्-फलितात समाविष्ट करण्याकरिता `graphicx` हा आज्ञासंच वापरला जातो. ह्या
आज्ञासंचातर्फे `\includegraphics` ही आज्ञा लाटेक्-ला पुरवली जाते.

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}

\begin{document}
This picture
\begin{center}
  \includegraphics[height=2cm]{example-image}
\end{center}
is an imported PDF.
\end{document}
```

EPS, PNG, JPG व PDF इत्यादी स्वरूपातील दृश्यधारिका ह्या आज्ञासंचातर्फे समाविष्ट करून घेता
येतात. तुमच्याकडे एकाच नावाच्या वेगवेगळ्या स्वरूपातील धारिका असतील, तर तुम्ही तुम्हाला हव्या
असलेल्या स्वरूपाचा फलितात समावेश करून घेण्याकरिता धारिकेचा प्रत्यय लिहू शकता, अन्यथा
आज्ञासंचामार्फत कोणत्याही स्वरूपाची धारिका समाविष्ट केली जाते.

तुम्ही हे पाहिलेच असेल की आपण इथे `center` नावाचे क्षेत्र वापरले आहे. ह्या क्षेत्राचा वापर
दृश्यकाची मांडणी कागदाच्या (आडव्या अक्षावर) मध्यभागी व्हावी म्हणून करण्यात आला आहे. [किंचित
पुढे](lesson-) आपण मोकळ्या जागा व स्थाननिश्चितीबाबत शिकणार आहोत.

## दृश्यरूपात बदल करणे

`\includegraphics` ह्या आज्ञेस अनेक प्राचले आहेत. त्यांमार्फत समाविष्ट दृश्यकाची उंची, रुंदी
निश्चित करण्यास मदत होते. तसेच ह्या प्राचलांसह दृश्यकास किंचित कापताही येते. ह्यांपैकी काही
प्राचले सतत वापरली जातात, त्यामुळे त्यांबद्दल माहिती घेणे उपयुक्त ठरू शकते.

सर्वात आवश्यक व वारंवार लागणारी प्राचले रुंदी व उंची निश्चित करण्यासाठीची. त्यांकरिता अनुक्रमे
`width` अथवा `height` ही प्राचले वापरली जातात. ही मापे बहुतांश वेळा मजकुराची रुंदी
(`\textwidth`) अथवा दस्तऐवजात चालू असलेली रुंदी (`\linewidth`) अथवा दस्तऐवजाची उंची
(`\textheight`)ह्यांची असतात. `\textwidth` व `\linewidth` ह्यांत सूक्ष्म फरक आहे. बहुतांश
वेळा त्यांचे फलित सारखेच असते, परंतु `\textwidth` ही मजकुराच्या चालू ठोकळ्यातील मजकुराची रुंदी
आहे. `\linewidth` मात्र **चालू** रुंदी आहे, जी स्थानपरत्वे वेगवेगळी असू शकते. (खासकरून द्विस्तंभीय
दस्तऐवजांत). ही प्राचले न वापरल्यास लाटेक्-तर्फे दृश्यकाची मापे आपोआप निवडली जातात. त्यात
दृश्यकाची परिमाणे गुणोत्तराने योग्य राखण्यासाठी प्रयत्न केला जातो.

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}

\begin{document}
\begin{center}
  \includegraphics[height = 0.5\textheight]{example-image}
\end{center}
Some text
\begin{center}
  \includegraphics[width = 0.5\textwidth]{example-image}
\end{center}
\end{document}
```
दृश्यकाचे आकारमान ठरावीक पटींनी वाढवण्याकरिता `scale` हे प्राचल वापरता येते. त्याला ठरावीक
कोनामध्ये फिरवण्यासाठी `angle` हे प्राचल वापरता येते. `clip` तसेच `trim` ह्या प्राचलांचा
वापर करून दृश्यकातील शुभ्र भाग कापून मुख्य भागच दिसेल अशी व्यवस्थाही करता येतेे.

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}

\begin{document}
\begin{center}
  \includegraphics[clip, trim = 0 0 50 50]{example-image}
\end{center}
\end{document}
```

## दृश्यकांची स्थाननिश्चिती

अक्षरजुळणी करताना, विशेषतः तांत्रिक दस्तऐवजांमध्ये दृश्यकांची जागा बदललेली दिसू शकते.
ह्याला `तरंगते दृश्यक` म्हटले जाते (इंग्रजी: float). दृश्यकांचा समावेश बहुतांश वेळा तरंगता
होतो. ह्यामुळे पानावर अनावश्यक मोकळी जागा सुटत नाही.

```latex
\documentclass{article}
\usepackage[T1]{fontenc}
\usepackage{graphicx}
\usepackage{lipsum}  % नमुना मजकूर छापण्याकरिता

\begin{document}
\lipsum[1-4] % काही नमुना परिच्छेद

Test location.
\begin{figure}[ht]
  \centering
  \includegraphics[width=0.5\textwidth]{example-image-a.png}
  \caption{An example image}
\end{figure}

\lipsum[6-10] % पुन्हा काही नमुना परिच्छेद
\end{document}
```

ह्या आज्ञावलीच्या फलितात दृश्यक लाटेक्-तर्फे `Test location` ह्या मजकुरापासून दूर हलवले
जाते. ह्याचे कारण पृष्ठाच्या तळाशी त्या छायाचित्राकरिता पुरेशी जागा नाही. `ht` ही प्राचले,
दृश्यकाचे स्थान निश्चित करतात. ह्या दोन प्राचलांमार्फत आज्ञावलीतील स्थानानुसार जिथे आहे तिथेच
(वरील उदाहरणात `Test location` ह्या मजकुराशेजारी) अथवा पृष्ठाच्या शीर्षस्थानी दृश्यकाची
मांडणी करण्याची आज्ञा लाटेक्-ला मिळते. चार प्रकारची प्राचले वापरली जाऊ शकतात. ती
पुढीलप्रमाणे.

- `h` (शक्यतः) **इथे**
- `t` पृष्ठाच्या शीर्षस्थानी
- `b` पृष्ठाच्या तळाशी
- `p` केवळ तरंगत्या दृश्यकांसाठीच्या पानावर

[लवकरच](lesson-09) आपण तरंगत्या दृश्यकांना अंतर्गत संदर्भ कसा द्यावा ते पाहणार आहोत. त्यामुळे
दस्तऐवजात त्यांचा निर्देश करणे सोपे होईल.

तुम्हाला कदाचित लक्षात आले असेलच की दृश्यकाची मांडणी दस्तऐवजाच्या मधोमध करण्यासाठी
`\centering` ह्या आज्ञेचा वापर आपण केला आहे. तरंगत्या दृश्यकांमध्ये सामग्री मध्यभागी
छापण्यासाठी `center` हे क्षेत्र न वापरता, `\centering` ही आज्ञा वापरणे अधिक श्रेयस्कर
ठरते. ह्यामुळे `center` क्षेत्रातर्फे सुटणारी अधिकची मोकळी जागा टाळली जाते.

## स्वाध्याय

तुमच्या पसंतीचे एखादे दृश्यक लाटेक्-आज्ञावलीत समाविष्ट करून पाहा. ह्यासाठी उदाहरणांमध्ये वापरलेली
दृश्यके सोडून दुसरे एखादे दृश्यक शोधा व ते समाविष्ट करा.


`height`, `width`, `angle` व `scale` ह्या प्राचलांसह काय काय करता येऊ शकते ते प्रयोग
करून पाहा.

`width` प्राचलाचा वापर करून, मजकुराच्या ठोकळ्याच्या रुंदीचे दृश्यक समाविष्ट करून पाहा व नंतर
पृष्ठाच्या चालू रुंदीचे दृश्यक समाविष्ट करून बघा. ह्यासाठी आपण वर पाहिल्याप्रमाणे अनुक्रमे
`\textwidth` व `\linewidth` ह्या दोन आज्ञा आहेत. लाटेक्-वर्गास `twocolumn` हे प्राचल
वापरून व न वापरता ह्या आज्ञांचे फलित कसे दिसते ते पाहा.

`lipsum`सह एक दीर्घ मजकूर असणारा दस्तऐवज बनवा. त्या आज्ञावलीत तरंगती दृश्यके
वापरा. निरनिराळी प्राचले वापरून, त्यांची स्थाननिश्चिती करा. ही प्राचले एकमेकांसह कशी काम
करतात त्याचे निरीक्षण करा.