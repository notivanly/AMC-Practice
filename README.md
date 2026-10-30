# Problem bank tools

`data/problems.js` is generated. Edit the `bank8.py`, `bank10.py` and `bank12.py` files, then run:

    pip install sympy
    python3 tools/build.py

Each problem is one call:

    P(10, 'alg', 3, 'Quadratics & Vieta',          # contest, topic, difficulty 1-5, subtopic
      r"Let $r$ and $s$ be the roots of $x^2-7x+5=0$. What is $r^2+s^2$?",
      '39', ['19','29','34','49'],                 # correct answer, four wrong answers (LaTeX)
      49 - 2*5,                                    # the answer computed independently, used as a check
      "Write r^2+s^2 using r+s and rs.",           # hint
      r"By Vieta, $r+s=7$ and $rs=5$, so $r^2+s^2=(r+s)^2-2rs=39$.")  # solution

The build sorts the choices from smallest to largest (like the real contest), spreads the correct
letter evenly across A to E, and **stops with an error if the correct answer does not match the
independently computed value**, so a typo can't ship a wrong answer key.
