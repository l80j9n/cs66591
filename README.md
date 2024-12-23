java c
CQF   Exam   One 
June   2024   Cohort 
Instructions All   questions   must   be   attempted.      Requested   mathematical   and   full   computational   workings   must   be   provided to obtain   maximum   credit.    CQF   material   and books   may be referred   to   but   you   should   answer   the   questions in your own words.   You   are   not   allowed   to   discuss   the   exam   work   with   anyone   else.
Upload two files:      E1 YOURNAME REPORT.pdf   and   E1 YOURNAME CODE.zip.    ZIP   file   to   include   source   code,   signed   declaration   (if not   in   PDF).   Use   YOURNAME   as   registered   on   CQF   Portal.
You   must   prepare   PDF   REPORT that integrates workings, numerical answers and plots in   the   order   of   questions.   Guide   to   report   preparation:
1.   If   you   draft   the   report   from   Python   notebook   –   remove   unnecessary   output   and   unused   code,   add maths with   Markdown   TeX.   Save   IPYNB   file to   HTML   first, then   print   PDF.
2.   If   you   draft   from   Word/LaTeX   –   add   maths   requested,   numerical   solutions   and   plots.      Here   you   can   insert   code   at   your   discretion,   eg   full/part   code   after   each   question   or   in   an   appendix.
3.      Exam   tasks   give   specific   instructions, eg   to   organise   results   into   a   table   or   specific   plot.   Handwritten    scanned   math   workings   are   acceptable   without   loss   in   marks.
4.    ‘Code+output’   Python   printouts   (absent   maths,   explanation,   issues   with   plots)   or   Excel   printouts   will   not   be   considered   full   reports.Making   operational   sense   of   exam   questions   and   coding   is   part   of   your   individual   exam   work.      Please make   a   good   use   of   lectures,   solutions   and   labs/tutorials.    Tutor   is   unable   to   confirm   formulae,   discuss your   numerical   answers   or   provide   hints   beyond   ones   given.
Exam   submissions   and   file   names   which   do   not   follow   these   instructions   will   require   extra   processing time.   Exam   One   computation   in   Excel   is   not   recommended.
Marking Scheme: Q1 16% Q2 24% Q3 8% Q4 28% Q5 24%.            Total   is   100%.
Exam One June 2024. Optimal Portfolio Allocation 
An   investment   universe   of the   following   risky   assets with   a   dependence   structure   (correlation)   applies to   all   questions   below   as   relevant:

Question 1. Global   Minimum   Variance   portfolio   is   obtained   subject   to   the   budget   constraint:

• Derive   the   analytical   solution   for   optimal   allocations w* .   Provide   full   derivation   workings.
•    Compute optimal   allocations   (Global   MV   portfolio)   for   the   given   investment   universe.
Question 2. Consider   the   optimization   for   a   target   return   m.   There   is   no   risk-free   asset.

•    Compute   correlation   levels   by   stressing   the   matrix   ×   1,   ×1.3,   ×1.8,   subject   to   the   upper   limit   0.99   for   each   cross-asset   correlation.   Diagonal   elements   stay   equal   to   one.
• Compute w*    and   portfolio   risk σΠ = √w′Σw   for   m   = 7%   for   three   levels   of   correlation   given.Hints:   it is possible to compute this   kind   of optimal   allocation   via   analytical   formula.    Negative and   non-   robust   allocations   (into   ±   100s%)   are   possible,   particularly   for   high   correlation.   Please   do   not   reconfirm your   n代 写CQF Exam OnePython
代做程序编程语言umerical   results   via   support.
Question 3. “Evaluating the PL more frequently   make it appear   more   risky than   it   actually   is.”   Make   the   following   computations   to   demonstrate   this   statement.
• Write   down   the   formula   for   Sharpe   Ratio   and   note   that σ is   scaled   with   time.
•    Compute   Daily,   Monthly,   and   Quarterly   Sharpe   Ratio,   for   Annualised   SR   of   0   .53.    Hint:   this   is   an abstract   computation, not   related   to   Questions   1   and   2.
•    Convert each   Sharpe   Ratio   into   Loss   Probability   (daily,   monthly,   quarterly,   annual),   using
Pr(PL < 0) = Pr(x < −SR). 
where   x   is   a   standard   Normal   random   variable.
Exam One June 2024. Understanding Value-at-Risk 
Assume   you   are   an   analyst   concerned   with   how   risky NASDAQ-100 became   over SP 500.   Perform. the   backtesting   of   Analytical   VaR   (99%/10day)   on   the   data   provided   in   .csv   files.
Question 4. The   quick   guide   is   given   below,   but   please   refer   to   the   tutorial   and   CQF   material.
VaR10D,t      = Factor   × σt    × √10 
•    Compute   the   rolling   standard   deviation   σt    from   21   daily   returns.    Timescale   of   σt    remains   ‘daily’   regardless   of how   many   returns   are   in   the   sample.
• To   make   a   projection   over   10   days,   we   use   the   additivity   of   variance σ10D    = √σt(2) × 10.
• A   breach   occurs   when   the   forward   realised   10-day   return   is   below   the   VaRt      quantity.
r10D,t+10         < VaR10D,t given both numbers are negative.
VaR is fixed at time t and compared to the return   from   t   to   t+10,   computed   ln(St+10/St   ).   Alternatively,   you   can   compare to   ln(St+11/St+1)   but   state this   assumption   in your   report   upfront.
Prepare   and   present   the   following   deliverables   in   your   report:
(a)    The   count   and   percentage   of VaR   breaches.
(b)    Provide   a   plot   which   identifies   the   breaches   with   crosses   or   other   marks.
(c)      Provide   a   list   of   breaches   with   columns   [Date,   ClosingPrice,   LogReturn, VaR   10D,   Ret   10D]. Hint:   you   need   to   have   True/False   breach   indicator   column   in   Python,   and   filter   with   ‘==   True’   .
(d)   In   your   own   words   describe,   was   NASDAQ-100   more   risky   than   SP   500   during   COVID   pandemic news   2020-Feb   to   2020-Mar?   What   about   the   subsequent   market   correction   period   in   2021-2022?
Question 5. Implement   the   backtest   of   VaR10D,t      but   now   with   the   input   of   EWMA  from   the
filtering   formula   below,   instead   of rolling   std   dev.   Tutor   will   not   reconfirm   the   formula/computation.

with   λ = 0.72   value   set   to   minimise   out   of   sample   forecasting   error.
Hint:   use   the   variance   for   the   entire   dataset   to   initialise   the   computation.
(a-c)    Provide   the   same   deliverables   (a),   (b)   and   (c)   as   in   the   previous   Question.
(d)      Briefly   discuss   the   impact   of   λ   on   smoothness   of   EWMA-predicted   volatility   (3-4 lines).
Hint:      you   can   discuss    λ   theoretically   without   recomputing   EWMA-based   backtest   but,    if   you   recompute   for   an   extra   illustration   it   is   sufficient   to   do   so   for   one   market   index   only.





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
