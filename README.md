# Natural Language Processing and Named Entity Recognition

This tutorial was written by <a href="https://www.grinnell.edu/users/waldenka">Katherine Walden</a>, Digital Liberal Arts Specialist at Grinnell College. Tutorial instructions were co-authored by Sarah Purcell (L.F. Parker Professor of History, Grinnell College) and Papa Ampim-Darko, a student research assistant at Grinnell College.

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist, Grinnell College).

This tutorial is adapted from Michelle Moravec’s <a href="http://historyinthecity.blogspot.com/2014/06/how-to-use-stanfords-ner-and-extract.html">History in the City Stanford NER tutorial</a> and Rachel Burma’s <a href="https://github.com/rbuurma/rise-2015">The Rise of the Novel Robinson Crusoe NER assignment</a>.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Natural Language Processing (Stanford’s Named Entity Recognizer) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

<hr />

Developed in 2006 by a team based out of Stanford University’s National Language Processing Group, the Stanford <a href="https://nlp.stanford.edu/software/CRF-NER.shtml#History">Named Entity Recognizer</a> (NER) is a Java-based tool for recognizing and extracting named entities in an unstructured textual dataset. In this tutorial, we’ll be using Stanford’s NER to identify named entities in <em>The Interesting Narrative of the Life of Olaudah Equiano, Or Gustavus Vassa, The African</em>, an autobiographical slave narrative published in 1789.

<hr />

## Data

1-Download the Equiano_Text.txt file from this Repo. Open the <strong>Equiano.txt</strong> file to see <a href="http://www.gutenberg.org/ebooks/15399?msg=welcome_stranger">the plain text utf-8 file</a> downloaded from Project Gutenberg.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture-1.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture-1.PNG?raw=true" alt="" width="780" height="959" /></a></p>

2-Copy the file to your <strong>Desktop</strong>, and <strong>right click on the file</strong> to open it in <strong>Notepad</strong>, the native Windows text editing program.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_12.PNG?raw=true" alt="" width="840" height="439" /></a></p>

3-Because the text file was downloaded from Project Gutenberg, it contains information at the beginning and end of the file that is not part of the original <em>Equiano</em> text. Delete these lines, re-save the file to your Desktop, and close Notepad.

<hr />

## Opening Stanford’s NER 

4-To install on your own computer, visit the program’s <a href="https://nlp.stanford.edu/software/CRF-NER.shtml#Download">Download page</a>.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_3.PNG?raw=true" alt="" width="927" height="682" /></a></p>

5-To open the program, navigate to C:\Program Files (x86)\Stanford NER and double click on the Windows Batch File named <strong>ner-gui</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_4.PNG?raw=true" alt="" width="657" height="653" /></a></p>

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_5.PNG?raw=true" alt="" width="676" height="339" /></a></p>

6-The program will launch two windows—a Command Prompt shell that will run the program via the CLI, and a GUI interface. Both windows need to remain open for the program to run.

<hr />

## Loading data into the NER

7-<strong>Erase the sample text</strong> in the GUI interface window.

8-Click <strong>File-&gt;Open File</strong>, and select the <strong>Equiano.txt</strong> file saved to your Desktop.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_6.PNG?raw=true" alt="" width="655" height="656" /></a></p>

9-Text will appear in the GUI window once the file has loaded.

<hr />

## Identifying Classifiers in the NER

10-Next, we need to load a list of sample terms for the NER to use when analyzing our text.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Pic_2.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Pic_2.png?raw=true" alt="" width="225" height="127" /></a></p>

11-Click <strong>Classifier-&gt;Load CRF from File</strong>. Navigate to C:\Program Files (x86)\Stanford NER\classifiers and open the classifiers folder.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_7.PNG?raw=true" alt="" width="524" height="363" /></a></p>

12-Stanford’s NER includes classifier resource files with 3, 4, and 7 entity categories it can search for in your text.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_8.PNG?raw=true" alt="" width="659" height="660" /></a></p>

13-Select the <strong>english.all.3class.distim.crf.ser.gz</strong> file and click the <strong>Open</strong> icon. Three entity categories (organization, location, person), with color labels, will now display on the right-hand side of the GUI window.

14-Click on the <strong>Run NER icon</strong> on the bottom of the GUI window to run the program.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_9.PNG?raw=true" alt="" width="675" height="337" /></a></p>

15-You can see the results being generated from the NER program in the CLI window.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_10.PNG?raw=true" alt="" width="659" height="651" /></a></p>

16-The GUI window now shows the color-coded results of the NER program’s analysis.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Pic_1.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Pic_1.png?raw=true" alt="" width="80" height="73" /></a></p>

17-The GUI interface gives you options to export your tagged file. Click <strong>File-&gt;Save Tagged File As</strong>. Navigate to your Desktop and save the file as <strong>Equiano_Tagged.txt.</strong>

18-You could also copy the text generated in the CLI and paste into a text file to see a list with just the tagged entities.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_11.PNG?raw=true" alt="" width="840" height="439" /></a></p>

19-Right click on the icon for the <strong>Equiano_Tagged.txt</strong> file and open in <strong>Notepad</strong>.

20-You’ll see that the NER has added &lt;LOCATION&gt;, &lt;PERSON&gt;, or &lt;ORGANIZATION&gt; tags around the entities it recognized based on the terms in the classification file. We could use a combination of XML and XPath to isolate terms with particular tag categories.

<hr />

## Reflection questions

<ul>
 	<li><em>Scroll down and see how accurate the NER was in identifying and tagging elements in the text. What errors or problems do you notice? How would those errors impact analysis of this text?</em></li>
 	<li><em>How did the process of using the NER impact or shape your understanding of the original text?</em></li>
 	<li><em>What kinds of historical research questions could a tool like Stanford’s NER help address?</em></li>
 	<li><em>What types of questions would not be a good fit for Stanford’s NER?</em></li>
 	<li><em>What problems or limitations can you see for using Stanford’s NER as a tool for historical analysis?</em></li>
</ul>
&nbsp;

<hr />

## Validating Tagged Entities as an XML Document

21-The output of the NER program is a text file with tagged elements. To prepare for Friday’s experimental lab, we’ll be importing that data into an Excel document so we have a list of the tagged entities.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true"><img class="aligncenter size-large wp-image-716" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_14.PNG?raw=true" alt="" width="676" height="356" /></a></p>

22-Open the <strong>Equiano_Tagged.txt</strong> file in Notepad. Click <strong>File—Save As</strong> to save a second copy of the NER output.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true"><img class="aligncenter size-full wp-image-715" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_13.PNG?raw=true" alt="" width="954" height="537" /></a></p>

23-Notepad’s default settings will save the file as a plain-text (.txt) file. We want to save the output as an extensible markup language (.xml) file to be able to extract the tagged entities.

24-In the File name box, add <strong>.xml</strong> to the end of the file name. Save the XML file to your Desktop.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_18.PNG?raw=true"><img class="aligncenter size-large wp-image-720" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_18.PNG?raw=true" alt="" width="676" height="356" /></a></p>

25-Navigate to <a href="https://codebeautify.org/xmlvalidator#">https://codebeautify.org/xmlvalidator#</a> in a web browser to validate your XML

&nbsp;

<blockquote><em>Free online validators can be a useful tool to identify errors or problems in a variety of file types (XML, HTML, JSON, etc.).</em></blockquote>

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true"><img class="aligncenter size-large wp-image-721" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_19.PNG?raw=true" alt="" width="676" height="339" /></a></p>

26-Copy the text in the <strong>Equiano_Tagged</strong> file, and paste it into the XML validator. Click <strong>Validate</strong> to check your XML.

27-The XML validator identifies an error in Line 1 of our Equiano data.

28-The <a href="https://www.w3schools.com/xml/xml_syntax.asp">World Wide Web Consortium (W3C) guidelines</a> say that valid XML has to declare a root element at the start the XML document.

29-Add <strong>&lt;root&gt;</strong> to the first line of your XML, and <strong>&lt;/root&gt;</strong> at the end of your XML.

30-Re-paste your text into the XML validator, and run the Validator again.

31-We have another error in Line 518 of our XML.

<blockquote><em>The ampersand symbol has a special function/meaning in XML, meaning the “&amp;c.” combination of characters will cause errors in validating or loading the XML.</em></blockquote>

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true"><img class="aligncenter size-large wp-image-722" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_20.PNG?raw=true" alt="" width="676" height="356" /></a></p>

&nbsp;

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_21.PNG?raw=true"><img class="aligncenter size-full wp-image-723" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_21.PNG?raw=true" alt="" width="347" height="188" /></a></p>

32-Go to <strong>Edit—Replace</strong> in Notepad. Instruct the program to find all instances of “&amp;c.” and replace them with “etc.”. Click <strong>Replace All</strong>.

33-Save the XML file, re-paste into the Validator, and validate once again.

34-We now have valid XML to load into Microsoft Excel.

<hr />

## Loading XML Data into Excel
 
<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_23.PNG?raw=true"><img class="aligncenter size-large wp-image-725" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_23.PNG?raw=true" alt="" width="676" height="374" /></a></p>

35-Open Microsoft Excel. Click <strong>File—Options</strong> to open the Excel Options window.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true"><img class="aligncenter size-full wp-image-724" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_22.PNG?raw=true" alt="" width="832" height="683" /></a></p>

36-Under <strong>Customize Ribbon</strong>, check the box next to <strong>Developer</strong> to enable the Developer tools. Click OK.

37-A <strong>Developer tab</strong> should now be visible in the top-level menu.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_24.PNG?raw=true"><img class="aligncenter size-full wp-image-726" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_24.PNG?raw=true" alt="" width="991" height="222" /></a></p>

38-Click on the <strong>Developer</strong> tab, and select <strong>Import</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_25.PNG?raw=true"><img class="aligncenter size-full wp-image-727" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_25.PNG?raw=true" alt="" width="950" height="538" /></a></p>

39-Select the <strong>Equiano_Tagged</strong> XML file and click Import.

40-We still have a variety of parsing errors in our XML file. Click on <strong>Details</strong> to view the specific line for each error.

41-You can go back into the Validator to view that line, or open the file in Notepad++ to identify and correct these errors.

42-Save the file after correcting each error, and retry the import into Excel.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_26.PNG?raw=true"><img class="aligncenter size-full wp-image-728" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_26.PNG?raw=true" alt="" width="426" height="131" /></a></p>

43-Once all the errors have been resolved, click <strong>OK</strong> on the window the pops up.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_27.PNG?raw=true"><img class="aligncenter size-full wp-image-729" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_27.PNG?raw=true" alt="" width="265" height="159" /></a></p>
 
44-You can add the data to an existing worksheet, or import it to a new worksheet. Click <strong>OK</strong>.

<p align="center"><a href="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_28.PNG?raw=true"><img class="aligncenter size-large wp-image-730" src="https://github.com/kwaldenphd/NLP-NER-tutorial/blob/master/screenshots/Capture_28.PNG?raw=true" alt="" width="676" height="376" /></a></p>

45-You can now see the entities tagged in the NER as distinct columns of Location, Person, and Organization.

46-From here, we could isolate Locations to map in a GIS system. Or, we could look at Persons and Organizations to build a network graph.

<hr />

# Reflection Questions:

<ul>
 	<li><em>What changes did you make to the XML file to allow Excel to import it? </em></li>
 	<li><em>How could these changes impact the meaning(s) of the original text? </em></li>
 	<li><em>Why do you think these changes are necessary? </em></li>
 	<li><em>What is gained or lost by going through this process manually (by hand) versus automating these changes?</em></li>
 	<li><em>Now that you have extracted a list of tagged entities, what could you do next with this data?</em></li>
 	<li><em>What questions do you have about this data? How could you use textual analysis methods/tools to address or answer those questions?</em></li>
</ul>
