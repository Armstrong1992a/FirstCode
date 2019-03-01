#include "number.h"
#include "exp10to2.h"

void exp10ToExp2(struct Number *pn)
{
while(pn->exp10<0)
  {
    while(pn->mantissa <= (UINT64_MAX-5)/2)
    {
        pn->mantissa = (pn->mantissa*2);
        pn->exp2 = pn->exp2 - 1;
    }
    pn->mantissa = ((pn->mantissa+5)/2);
    pn->exp10 = pn->exp10 + 1;
  }
}

