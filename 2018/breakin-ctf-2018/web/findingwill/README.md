<h3 id="break-in-2018-connecting-will"><strong>Break In 2018 - Connecting Will</strong></h3>

<hr>

<p><strong>Description</strong></p>

<p><a href="https://felicity.iiit.ac.in/contest/breakin/findingwill/">https://felicity.iiit.ac.in/contest/breakin/findingwill/</a></p>
<p>
Will is lost in the Upside-Down and is stuck with the Demogorgon. El is looking for Will, when, she stumbles across a piece of code that Will wrote. The Demogorgon could not decipher the code and hence just left it lying around. El needs your help to find the 2 numbers that can get her the secret key which Will was trying to share. Can you help her?
</p>

<hr>

<p><img src="https://raw.githubusercontent.com/0xy4hy4/Write-ups/master/2018/breakin-ctf-2018/web/findingwill/findingwill.png" alt="enter image description here" title=""></p>

<p>The website shows a login form with a First Number and a Last Number. From the given source code we can assume that we need to put 2 hashes that have the same value,  <br>
In order to solve this challenge we could look for a md5 collision</p>

<p>md5(‘240610708’) ‘s result is  0e462097431906509019562988736854</p>

<p>.</p>

<p>md5(‘QNKCDZO’) ‘s result is 0e830400451993494058024219903391.</p>

<p>0 == 0 when compared with == they give us True </p>

<p>but with this we will not be accessed because we have </p>

<pre><code>($hash1 != $hash2)
</code></pre>

<p>by looking on : </p>

<pre><code>$hash2 = strtr($hash2, “abcd”, “0123”);</code></pre>

<p>i use this site to get some hashes who started by  <br>
ae ;)  <br>
<a href="https://md5db.net/explore/ae46">https://md5db.net/explore/ae46</a></p>

<p>dlhkwp : ae46007dc4407b097dc1d216cd48d15d <br>
‘a’ will be replaced by 0 (0e)</p>

<p>so :  <br>
ae46007dc4407b097dc1d216cd48d15d != 0e462097431906509019562988736854 <br>
after that a,b,c,d will be replaced by 0,1,2,3 <br>
0e46007dc4407b097dc1d216cd48d15d <br>
0e460073244071097321321623483153 <br>
and  <br>
0e460073244071097321321623483153 equal 0e462097431906509019562988736854 (true)</p>

<p>first number : 240610708 <br>
last number : dlhkwp</p>

<p>Success. The flag is BREAKIN{I_Will_Connect}</p>
<p>#0v3n_Sh3ll ❤</p>
