#Analysis #Statistics #Robotics #ElectricalEngineering #ControlTheory #SignalProcessing
The Laplace Transform is defined as:
	$\mathscr{L}\{f(t)\} = F(s) = \int^\infty_0 f(t) \exp{(-st)} \text{d}t$

The Laplace transform turns differential and integral expression into algebraic expressions. One can solve equations in the frequency domain instead of the time domain. The integral must converge which is fulfilled for [[Linear]] $f(t)$.
## Examples

- $f(t) = a$; $\mathscr{L}\{f(t)\} = \frac{a}{s}$
- $f(t) = t$; $\mathscr{L}\{f(t)\} = \frac{1}{s^2}$
- $\mathscr{L}\{\dot{f}(t)\} = s F(s) - f(0)$
- $\mathscr{L}\{\int^t_0 f(t)\} = \frac{1}{s}F(s)$
- $f(t) = \exp{(-\alpha t)}$; $\mathscr{L}\{f(t)\} = \frac{1}{s+a}$
- $\mathscr{L}\{\delta(t)\} = 1$, where $\delta$ is the dirac delta function



![[Properties of the laplace transform.png]]