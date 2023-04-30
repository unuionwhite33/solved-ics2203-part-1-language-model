Download Link: https://assignmentchef.com/product/solved-ics2203-part-1-language-model
<br>
The first project will be related to building a language model from scratch. In the first instance, the first thing that is required is that you prepare a corpus (choose only one) and carry out the necessary preprocessing.




Maltese Corpus: <u>http://mlrs.research.um.edu.mt/index.php?page=downloads</u>

(Baby) British National Corpus: <u>http://ota.ox.ac.uk/desc/2553</u>







First set of tasks:

<ol>

 <li>Extract the selected corpus</li>

 <li>Build frequency counts for n-grams</li>

</ol>




Things to keep in mind:

<ul>

 <li>Try to make your code modular. Of course, initially hard coding stuff is ok. But ideally, evolve your hard-coding to generic, modular code</li>

 <li>You might also want to hard code a specific input string so that you can ensure that your frequency counts are correct.</li>

 <li>Consider computational issues – check how long it takes to read the corpus, build frequency counts, how well it scales up, amount of RAM that the system ends up using, etc.</li>

 <li>When reading the files, you might want to consider using one file initially. But already start investigating using all files in the corpus. Remember the larger your corpus, the better the models will be.</li>

 <li>Think ahead – Once you get the frequency counts sorted, remember that like in any machine learning set up, we will be needing a training set and a test set. So you will eventually need to split your corpus into two distinct parts. More about this at a later stage, but it is good that you start thinking about this eventuality.</li>

</ul>




<h1>Building a Language Model – Part II</h1>




Now that you have selected the corpus, extracted it and built your frequencies, you can now start working towards building a language model from scratch.




We will be building a language model that will include the Unigram, Bigram and Trigram models and we will be building three different langauge models




<ol>

 <li>The <strong>Vanilla Language model</strong> is your regular language model</li>

 <li>The <strong>Laplace Language model</strong> will take the Vanilla as its basis, but you will now include Laplace smoothing.</li>

 <li>The <strong>UNK Language model</strong> will take the Vanilla as its basis, but now you will set all the words that have a count of 2 or less as &lt;UNK&gt; tokens. And then recalculate accordingly. And recalculate Laplace smoothing on this model.</li>

</ol>




Next, create a function that will carry out <strong>Linear Interpolation</strong> – this function takes one of the above 3 flavours of language models and calculate the probability of a sentence using the following lambdas: trigram = 0.6; bigram = 0.3; unigram = 0.1.




<strong>Evaluation</strong>:

<ol>

 <li>Take the test corpus, iterate through the sentences and calculate the probabilites for each sentence with every model. You will then use this to calculate the <strong>Perplexity</strong> and produce the following table:</li>

</ol>




<table width="697">

 <tbody>

  <tr>

   <td width="139"> </td>

   <td width="125">Unigram</td>

   <td width="123">Bigram</td>

   <td width="132">Trigram</td>

   <td width="177">Linear Interpolation</td>

  </tr>

  <tr>

   <td width="139">Vanilla</td>

   <td width="125"> </td>

   <td width="123"> </td>

   <td width="132"> </td>

   <td width="177"> </td>

  </tr>

  <tr>

   <td width="139">Laplace</td>

   <td width="125"> </td>

   <td width="123"> </td>

   <td width="132"> </td>

   <td width="177"> </td>

  </tr>

  <tr>

   <td width="139">UNK</td>

   <td width="125"> </td>

   <td width="123"> </td>

   <td width="132"> </td>

   <td width="177"> </td>

  </tr>

 </tbody>

</table>




<ol start="2">

 <li>Create a function that allows the user to select one of the Language Models (Vanilla, Laplace, UNK) and input a phrase. The function will use this phrase to <strong>Generate</strong> the rest of the sentence until it encounters the end of sentence token (i.e. the LM says stop!)</li>

</ol>







<h1>Building a Language Model – Practicalities</h1>




Submission Requirements:

<ol>

 <li>Code &amp; Documentation – be concise – I don’t want an explanation of the class notes. I want an explanation of your implementation choices. I also accept a submission of a jupiter notebook with documentation integrated in it.</li>

 <li>Demo (arranged after submission)</li>

</ol>




Marking Scheme:

Preprocessing: 5 marks

Vanilla LM: 10 marks

Laplace LM: 10 marks

UNK LM: 10 marks

Interpolation: 10 marks

Perplexity Evaluation: 10 marks

Generation Evaluation: 10 marks

Documentation (justification of choices, etc.): 20 marks

Demo: 15 marks