A	Simple	Example	of	Code	Review (from	the	Book	of	“Applied	
Software	Project	Management” by	Andrew	Stellman	and	Jennifer	Greene):

public	class	Account	{	
double	principal,rate;	int	daysActive,accountType;
public	 static	 final	 int	 STANDARD=0,	 BUDGET=1,	 PREMIUM=2,	
PREMIUM_PLUS=3;
}
  ...
  public	static	double	calculateFee(Account[]	accounts)
  {
    double	totalFee	=	0.0;
    Account	account;
    for	(int	i=0;i<accounts.length;i++)	{
      account=accounts[i];
      if(account.accountType==Account.PREMIUM||	account.accountType	
      ==	Account.PREMIUM_PLUS	)	
      totalFee	+=	.0125	*	(	//	1.25%	broker's	fee
      account.principal*Math.pow
      (account.rate,(account.daysActive/365.25))	
												- account.principal);	//	interest-principal
    }
  return	totalFee;
}
