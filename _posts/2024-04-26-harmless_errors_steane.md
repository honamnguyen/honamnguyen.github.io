---
title: 'Should we worry about all errors in quantum code?'
date: 2024-04-26
permalink: /blog/harmless_errors_steane
author_profile: false
---

No, not necessarily.

I recently encountered the following observation in my research on fault-tolerant encoding:
<blockquote>
... no \(Z\) errors are harmful for \(|0\rangle_{\text{L}}\) encoded with the Steane code... Because of the \(Z\) stabilizer operators of \(|0\rangle_{\text{L}}\) given above, arbitrary \(Z\) errors are equivalent to no error or single-qubit \(Z\) errors. - <a href="https://www.nature.com/articles/srep19578">Goto</a>
</blockquote>
This is a powerful insight that allows the author to overlook all $$Z$$ errors to devise an efficient encoding circuit with minimal overhead. And yet, I still struggle to see where it comes from. Thankfully, a colleague of mine pointed out a simple recipe to convince myself that this is true. 

Consider an arbitrary multi-qubit $$Z$$ error:
1. If its weight is odd, apply 4-qubit $$Z$$ stabilizers until we are left with a weight-1 error.
2. If its weight is even, we can either:<br/>
    a. Play with 4-qubit $$Z$$ stabilizers to see if it reduces to the Identity<br/>
    b. Apply the logical $$Z$$ operator \\(Z_{\rm L} = ZZZZZZZ\\) to get an odd-weight error and go back to case 1<br/>
<br/><img src='/images/Zerrors_Steane.png'>

Now the question is: does this property extend to other CSS codes as well?