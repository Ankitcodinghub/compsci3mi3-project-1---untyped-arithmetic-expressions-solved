# compsci3mi3-project-1---untyped-arithmetic-expressions-solved
**TO GET THIS SOLUTION VISIT:** [COMPSCI3MI3 Project 1 – Untyped Arithmetic Expressions Solved](https://www.ankitcodinghub.com/product/compsci3mi3-project-1-untyped-arithmetic-expressions-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;92578&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;COMPSCI3MI3 Project 1 - Untyped Arithmetic Expressions Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
&nbsp;

Recall our language of Untyped Arithmetic Expressions from topics 3 and 4.

Each part of this project will require you to submit a separate Haskell source file. The file from part 1 is used in part 2, and the file from part 2 is used in part 3. Nevertheless, please keep the part 1, 2 and 3

material separated for the purposes of marking.

<h1>1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Implementation of Small Step Semantics</h1>
In Assignment 2, you were asked to enocode the grammar of UAE in the type system of Haskell. The time has come to add the small-step semantics.

When you have finished these tasks, save your Haskell source file as UAE1.hs, and submit it to the P1 Avenue dropbox.

<h2>1.1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Modifying Our Datatype</h2>
We will need to begin by creating two more data types, to represent both values and numeric values. Remove the value terms from your term data type, and create two new ones, conforming to the grammar given above.

This will become important later on in the project.

<ul>
<li>Think about the way v and nv are used in the small step sematics above.</li>
</ul>
<h3>NV⊂V⊂T</h3>
In order for UAE to work correctly, your two new value types will need to be <strong>subtypes </strong>of the term type. You can achieve this a couple different ways, but the easiest is as follows:

<table width="591">
<tbody>
<tr>
<td width="591">data SuperType = A | B | C | D SubType | E SubType SubType data SubType = X | Y | Z</td>
</tr>
</tbody>
</table>
1

2

3

The one complication to this is that you’ll need to specify both the supertype and subtype when pattern matching:

<table width="591">
<tbody>
<tr>
<td width="591">myfunc : : SuperType −<em>&gt; </em>. . . myfunc (A) = . . . myfunc (B) = . . . myfunc (C) = . . . myfunc (D X) = . . . myfunc (D Y) = . . . myfunc (D Z) = . . .</td>
</tr>
</tbody>
</table>
1

2

3

4

5

6

7

If you set things up in the manner specified above, you will cause a naming conflict between the successor function already defined in your term datatype and your new datatype for numeric values. If this is the case, rename the successor function in the numeric values datatype.

<h2>1.2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Single Step Semantics</h2>
Next write a Haskell function which encodes the small-step operational semantics given above. This function should accept an argument of the term type, and produce an output also of the term type. Call this function ssos, which stands for <em>small-step opeartional semantics</em>.

Just as your data type for terms should not have any of Haskell’s native data types in it (like boolean truth values or numbers), neither should your function. Points will be deducted for using Haskell’s native types.

In addition to the rules above, please add rules which cause all values to evaluate to themselves (i.e., add reflexivity for values, both boolean and numeric). This will be necessary later on. Some rules will rely on the distinction between succ t and succ nv. Anywhere in the above small step semantics you see the successor taking a numeric value, you should interpret that as the successor function in your NV datatype.

If you used the subtyping method from the previous question, you will need to add one more rule to the above to transform a successor to a value-successor. This is relatively straightforward:

succ nv→succval nv Where succval is the version of the successor defined in your NV set.

<ul>
<li>The reason for the above addition is this. Our semantics depend on the ability of certain terms to be able to distinguish between terms that are numeric values and terms that are not. Consider EPredSucc and E-IsZero. These terms only operate over numeric values. This becomes a problem with expressions such as the following:</li>
</ul>
iszero succ succ succ 0&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (1)

The only successor function that “knows” that it holds a numeric value is the last one. The others don’t have that information available. If however, we add the above evaluation rule, we can resolve this issue. A small amount of effort is also necessary to make sure that the other evaluation rules are looking for the correct version of succ, but once you’ve got it, the following:

<table width="591">
<tbody>
<tr>
<td width="574">pred succ succ succ pred pred succ succ succ 0

Will evaluate to…
</td>
<td width="17">(2)</td>
</tr>
<tr>
<td width="574">succval succval succval 0</td>
<td width="17">(3)</td>
</tr>
</tbody>
</table>
Otherwise, your final result will still have some instances of pred in it.

Here are some test cases, in case you want to check your work before submitting.

<table width="624">
<tbody>
<tr>
<td width="624"><em>&gt;&gt; </em>Pred $ Succ $ Succ $ Succ $ Pred $ Pred $ Succ $ Succ $ Succ $ NV Z

<em>&gt;&gt; </em>IfThenElse ( IsZero&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (Succ (NV Z) ) ) (V T) (Succ (NV Z) ) <em>&gt;&gt; </em>IsZero $ V T
</td>
</tr>
</tbody>
</table>
1

2

3

<h2>1.3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Multi-Step Semantics</h2>
Now that we have our small-step semantics roughed out, write a function to evaluate our terms, called eval. This function should repeatedly apply the single-step semantic to a term until the term can’t be evaluated further. How to figure out when a term can’t be evaluated further is left as an exercise to the student, but as a general hint, in UAE not all irreducible terms are values, so you can’t just evaluate until you get a value and call it a day!

<h1>2&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Dealing with Wrongness</h1>
We now have our grammar encoded, but we can still have behaviour within our language that we don’t want. Specifically, not all evaluation chains in our system terminate in a value (as you may have noticed). This is because our language lacks the ability to produce runtime errors for syntactically correct expressions. With expressions such as:

iszero true&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (4)

There is no rule which applies. The expression can’t be evaluated further, and the expression is not a value.

Let’s add a new value, wrong, which will be the result of evaluating nonsense terms, like the one above. The following is an incomplete set of the rules needed to implement wrong. In the following, BV will be the set of Boolean values (true and false), and NV will be the set of numeric values, as defined above.

∀<em>n </em>∈NV<em>,</em>∀<em>t</em><sub>2</sub><em>,t</em><sub>3 </sub>∈T <em>,</em>if <em>n </em>then <em>t</em><sub>2 </sub>else <em>t</em><sub>3 </sub>→wrong&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (E-If-Wrong)

∀<em>b </em>∈BV<em>,</em>succ <em>b </em>→wrong&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (E-Succ-Wrong)

∀<em>b </em>∈BV<em>,</em>pred <em>b </em>→wrong&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (E-Pred-Wrong)

∀<em>b </em>∈BV<em>,</em>iszero <em>b </em>→wrong&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (E-IsZero-Wrong)

In addition, you will need to add some more evaluation rules so that the following requirements are met. You are required to use the small-step semantic style to deal with these problems. (You can’t just call error!):

<ul>
<li>If, during normal execution, a wrong value is produced, the entire expression should evaluate to wrong.</li>
<li>You may need to add one or two additional rules to make your wrong term work the same way as the other values.</li>
</ul>
Nothing special is required in our evaluation function, an expression evaluating to wrong is good enough. When finished, name your file UAE2.hs, and submit it to the P1 Avenue dropbox.

<h1>3&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Big Step Semantics</h1>
The essential difference between big step and small step semantics is that, where the small step semantics must be looped to find an expression’s normal form, our big step semantics compute the entire result in one go.

Write a function, called bsos (Big Step Operational Semantics), which implements the following evaluation rules, which comprise the big-step semantics of UAE:

You are free to introduce the Wrong term anywhere it may be appropriate. In general, your big-step semantics should evaluate expressions to the same normal form given by the multi-step small step semantics. That is,

<em>t </em>→<sup>∗ </sup><em>t</em><sup>0 </sup>∧ <em>t </em>⇓ <em>t</em><sup>00 </sup>=⇒ <em>t</em><sup>0 </sup>= <em>t</em><sup>00&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </sup>(5)

When finished, name your file UAE3.hs, and submit it to the P1 Avenue dropbox.
