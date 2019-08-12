# Natural Language Processing and Named Entity Recognition

This tutorial was written by <a href="https://www.grinnell.edu/users/waldenka">Katherine Walden</a>, Digital Liberal Arts Specialist at Grinnell College. Tutorial instructions were co-authored by Sarah Purcell (L.F. Parker Professor of History, Grinnell College) and Papa Ampim-Darko, a student research assistant at Grinnell College.

This tutorial was reviewed by <a href="https://www.grinnell.edu/users/donovang">Gina Donovan</a> (Instructional Technologist, Grinnell College).

This tutorial is adapted from Michelle Moravec’s <a href="http://historyinthecity.blogspot.com/2014/06/how-to-use-stanfords-ner-and-extract.html">History in the City Stanford NER tutorial</a> and Rachel Burma’s <a href="https://github.com/rbuurma/rise-2015">The Rise of the Novel Robinson Crusoe NER assignment</a>.

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
Natural Language Processing (Stanford’s Named Entity Recognizer) is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

<hr />

Developed in 2006 by a team based out of Stanford University’s National Language Processing Group, the Stanford <a href="https://nlp.stanford.edu/software/CRF-NER.shtml#History">Named Entity Recognizer</a> (NER) is a Java-based tool for recognizing and extracting named entities in an unstructured textual dataset. In this tutorial, we’ll be using Stanford’s NER to identify named entities in <em>The Interesting Narrative of the Life of Olaudah Equiano, Or Gustavus Vassa, The African</em>, an autobiographical slave narrative published in 1789.

<hr />

<h5>Data</h5>
1-Open the <strong>File Explorer</strong> and navigate to \\storage\projects\HIS\HIS-295-02\Equiano_Text_File. Open the <strong>Equiano.txt</strong> file to see <a href="http://www.gutenberg.org/ebooks/15399?msg=welcome_stranger">the plain text utf-8 file</a> downloaded from Project Gutenberg.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture-1.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture-1.png" alt="" width="780" height="959" /></a>

2-Copy the file to your <strong>Desktop</strong>, and <strong>right click on the file</strong> to open it in <strong>Notepad</strong>, the native Windows text editing program.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_12.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_12-1024x535.png" alt="" width="840" height="439" /></a>

3-Because the text file was downloaded from Project Gutenberg, it contains information at the beginning and end of the file that is not part of the original <em>Equiano</em> text. Delete these lines, re-save the file to your Desktop, and close Notepad.

<hr />

<h5>Opening Stanford’s NER</h5>
4-The NER has already been downloaded and installed on the Library computers. To install on your own computer, visit the program’s <a href="https://nlp.stanford.edu/software/CRF-NER.shtml#Download">Download page</a>.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_3.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_3.png" alt="" width="927" height="682" /></a>

5-To open the program, navigate to C:\Program Files (x86)\Stanford NER and double click on the Windows Batch File named <strong>ner-gui</strong>.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_4.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_4.png" alt="" width="657" height="653" /></a><a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_5.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_5.png" alt="" width="676" height="339" /></a>

6-The program will launch two windows—a Command Prompt shell that will run the program via the CLI, and a GUI interface. Both windows need to remain open for the program to run.

<hr />

<h5>Loading data into the NER</h5>
7-<strong>Erase the sample text</strong> in the GUI interface window.

8-Click <strong>File-&gt;Open File</strong>, and select the <strong>Equiano.txt</strong> file saved to your Desktop.
<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_6.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_6.png" alt="" width="655" height="656" /></a>

9-Text will appear in the GUI window once the file has loaded.

<hr />

<h5>Identifying Classifiers in the NER</h5>
10-Next, we need to load a list of sample terms for the NER to use when analyzing our text.
<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Pic_2.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Pic_2.png" alt="" width="225" height="127" /></a>

11-Click <strong>Classifier-&gt;Load CRF from File</strong>. Navigate to C:\Program Files (x86)\Stanford NER\classifiers and open the classifiers folder.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_7.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_7.png" alt="" width="524" height="363" /></a>

12-Stanford’s NER includes classifier resource files with 3, 4, and 7 entity categories it can search for in your text.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_8.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_8.png" alt="" width="659" height="660" /></a>

13-Select the <strong>english.all.3class.distim.crf.ser.gz</strong> file and click the <strong>Open</strong> icon. Three entity categories (organization, location, person), with color labels, will now display on the right-hand side of the GUI window.

14-Click on the <strong>Run NER icon</strong> on the bottom of the GUI window to run the program.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_9.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_9.png" alt="" width="675" height="337" /></a>

15-You can see the results being generated from the NER program in the CLI window.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_10.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_10.png" alt="" width="659" height="651" /></a>

16-The GUI window now shows the color-coded results of the NER program’s analysis.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Pic_1.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Pic_1.png" alt="" width="80" height="73" /></a>

17-The GUI interface gives you options to export your tagged file. Click <strong>File-&gt;Save Tagged File As</strong>. Navigate to your Desktop and save the file as <strong>Equiano_Tagged.txt.</strong>

18-You could also copy the text generated in the CLI and paste into a text file to see a list with just the tagged entities.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_11.png"><img class="aligncenter" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/07/Capture_11-1024x535.png" alt="" width="840" height="439" /></a>

19-Right click on the icon for the <strong>Equiano_Tagged.txt</strong> file and open in <strong>Notepad</strong>.

20-You’ll see that the NER has added &lt;LOCATION&gt;, &lt;PERSON&gt;, or &lt;ORGANIZATION&gt; tags around the entities it recognized based on the terms in the classification file. We could use a combination of XML and XPath to isolate terms with particular tag categories.

<hr />

<h5>Reflection questions</h5>
<ul>
 	<li><em>Scroll down and see how accurate the NER was in identifying and tagging elements in the text. What errors or problems do you notice? How would those errors impact analysis of this text?</em></li>
 	<li><em>How did the process of using the NER impact or shape your understanding of the original text?</em></li>
 	<li><em>What kinds of historical research questions could a tool like Stanford’s NER help address?</em></li>
 	<li><em>What types of questions would not be a good fit for Stanford’s NER?</em></li>
 	<li><em>What problems or limitations can you see for using Stanford’s NER as a tool for historical analysis?</em></li>
</ul>
&nbsp;

<hr />

<h5><strong>Validating Tagged Entities as an XML Document</strong></h5>
21-The output of the NER program is a text file with tagged elements. To prepare for Friday’s experimental lab, we’ll be importing that data into an Excel document so we have a list of the tagged entities.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_14.png"><img class="aligncenter size-large wp-image-716" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_14-1024x540.png" alt="" width="676" height="356" /></a>

22-Open the <strong>Equiano_Tagged.txt</strong> file in Notepad. Click <strong>File—Save As</strong> to save a second copy of the NER output.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_13.png"><img class="aligncenter size-full wp-image-715" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_13.png" alt="" width="954" height="537" /></a>

23-Notepad’s default settings will save the file as a plain-text (.txt) file. We want to save the output as an extensible markup language (.xml) file to be able to extract the tagged entities.

24-In the File name box, add <strong>.xml</strong> to the end of the file name. Save the XML file to your Desktop.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_18.png"><img class="aligncenter size-large wp-image-720" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_18-1024x540.png" alt="" width="676" height="356" /></a>

25-Navigate to <a href="https://codebeautify.org/xmlvalidator#">https://codebeautify.org/xmlvalidator#</a> in a web browser to validate your XML

&nbsp;
<blockquote><em>Free online validators can be a useful tool to identify errors or problems in a variety of file types (XML, HTML, JSON, etc.).</em></blockquote>
<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_19.png"><img class="aligncenter size-large wp-image-721" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_19-1024x514.png" alt="" width="676" height="339" /></a>

26-Copy the text in the <strong>Equiano_Tagged</strong> file, and paste it into the XML validator. Click <strong>Validate</strong> to check your XML.

27-The XML validator identifies an error in Line 1 of our Equiano data.

28-The <a href="https://www.w3schools.com/xml/xml_syntax.asp">World Wide Web Consortium (W3C) guidelines</a> say that valid XML has to declare a root element at the start the XML document.

29-Add <strong>&lt;root&gt;</strong> to the first line of your XML, and <strong>&lt;/root&gt;</strong> at the end of your XML.

30-Re-paste your text into the XML validator, and run the Validator again.

31-We have another error in Line 518 of our XML.
<blockquote><em>The ampersand symbol has a special function/meaning in XML, meaning the “&amp;c.” combination of characters will cause errors in validating or loading the XML.</em></blockquote>
<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_20.png"><img class="aligncenter size-large wp-image-722" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_20-1024x540.png" alt="" width="676" height="356" /></a>

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_21.png"><img class="aligncenter size-full wp-image-723" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_21.png" alt="" width="347" height="188" /></a>

32-Go to <strong>Edit—Replace</strong> in Notepad. Instruct the program to find all instances of “&amp;c.” and replace them with “etc.”. Click <strong>Replace All</strong>.

33-Save the XML file, re-paste into the Validator, and validate once again.

34-We now have valid XML to load into Microsoft Excel.

<hr />

<h5><strong>Loading XML Data into Excel</strong>
<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_23.png"><img class="aligncenter size-large wp-image-725" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_23-1024x567.png" alt="" width="676" height="374" /></a></h5>
35-Open Microsoft Excel. Click <strong>File—Options</strong> to open the Excel Options window.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_22.png"><img class="aligncenter size-full wp-image-724" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_22.png" alt="" width="832" height="683" /></a>

36-Under <strong>Customize Ribbon</strong>, check the box next to <strong>Developer</strong> to enable the Developer tools. Click OK.

37-A <strong>Developer tab</strong> should now be visible in the top-level menu.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_24.png"><img class="aligncenter size-full wp-image-726" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_24.png" alt="" width="991" height="222" /></a>

38-Click on the <strong>Developer</strong> tab, and select <strong>Import</strong>.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_25.png"><img class="aligncenter size-full wp-image-727" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_25.png" alt="" width="950" height="538" /></a>

39-Select the <strong>Equiano_Tagged</strong> XML file and click Import.

40-We still have a variety of parsing errors in our XML file. Click on <strong>Details</strong> to view the specific line for each error.

41-You can go back into the Validator to view that line, or open the file in Notepad++ to identify and correct these errors.

42-Save the file after correcting each error, and retry the import into Excel.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_26.png"><img class="aligncenter size-full wp-image-728" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_26.png" alt="" width="426" height="131" /></a>

43-Once all the errors have been resolved, click <strong>OK</strong> on the window the pops up.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_27.png"><img class="aligncenter size-full wp-image-729" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_27.png" alt="" width="265" height="159" /></a>

44-You can add the data to an existing worksheet, or import it to a new worksheet. Click <strong>OK</strong>.

<a href="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_28.png"><img class="aligncenter size-large wp-image-730" src="http://sarahjpurcell.sites.grinnell.edu/digital_methods/wp-content/uploads/2018/11/Capture_28-1024x569.png" alt="" width="676" height="376" /></a>

45-You can now see the entities tagged in the NER as distinct columns of Location, Person, and Organization.

46-From here, we could isolate Locations to map in a GIS system. Or, we could look at Persons and Organizations to build a network graph.

<hr />

<h5><em>Reflection Questions:</em></h5>
<ul>
 	<li><em>What changes did you make to the XML file to allow Excel to import it? </em></li>
 	<li><em>How could these changes impact the meaning(s) of the original text? </em></li>
 	<li><em>Why do you think these changes are necessary? </em></li>
 	<li><em>What is gained or lost by going through this process manually (by hand) versus automating these changes?</em></li>
 	<li><em>Now that you have extracted a list of tagged entities, what could you do next with this data?</em></li>
 	<li><em>What questions do you have about this data? How could you use textual analysis methods/tools to address or answer those questions?</em></li>
</ul>
