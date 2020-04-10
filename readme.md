# Successor

Make every the sum, the multiplication and the power-of operation with only the use of s2, with add 1 to the input

ANSWER:

(define s2<br/>
&emsp;(lambda (u v)<br/>
&emsp;&emsp;(+ 1 v)<br/>
&emsp;)<br/>
)<br/>

;(s2 1 2)<br/>
;(s2 1 7)<br/>
;(s2 1 10)<br/>
;(s2 1 21)<br/>

(define H<br/>
&emsp;(lambda (f g) ;f: valore in forma di procedura   g: operazione più bassa<br/>
&emsp;&emsp;(lambda (m n) ;m=primo valore ;n=secondo valore<br/>
&emsp;&emsp;&emsp;(if(= n 0)<br/>
&emsp;&emsp;&emsp;&emsp;(f m)<br/>
&emsp;&emsp;&emsp;&emsp;(g m ((H f g) m (- n 1) )); Generic formula<br/>
&emsp;&emsp;&emsp;&emsp;)<br/>
&emsp;&emsp;&emsp;)<br/>
&emsp;&emsp;)<br/>
)<br/>

(s2 1 10)<br/>
(define add (H (lambda (x) x) s2))<br/>
(add 5 3)<br/>
(define mul (H (lambda (x) 0) add))<br/>
(mul 5 3)<br/>
(define pow (H (lambda (x) 1) mul))<br/>
(pow 5 3)<br/>