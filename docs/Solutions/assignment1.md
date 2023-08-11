# Assignment 1: Debye, Drude, Sommerfeld, and chemistry

The first assignment can be found [here](../assignments/Assignmentfour.pdf)

## Exercise 1 - Debye

1. What are the assumptions of the Debye model?

    The Debye model considers only sound waves in a material (i.e. one assumes a linear dispersion $\omega = v k$) which oscillate up to a maximum frequency $\omega_{\mathrm{cutoff}} = \omega_d$, the Debye frequency, which exists to ensure that the total number of vibrational modes in the system is correct (equal to the number of degrees of freedom in the system).

2. Write an expression for the number of modes in a two-dimensional system, and thus determine the _Debye wavenumber_ (the wavenumber which corresponds to the Debye frequency).

    In two dimensions, there should be $2N$ modes (we implicitly assume that the different sound polarisations propagate with the same velocity, and thus

    $$
    2N = 2 \frac{A}{2\pi^2} \int_0^{|k| = k_d} \mathrm{d}^2 k
    $$

    where $A$ is the area of our periodic system ($L \times L$). The integral is simply the area of a circle with a radius $k_d$, so it evaluates to

    $$
    2N = \frac{2A}{(2\pi)^2}(\pi k_d^2)
    $$

    and ultimately obtains

    $$
    k_d = \sqrt{4\pi n}
    $$

    with $n = N/A$ (the two-dimensional density).

3. Provide a brief discussion of which elements you would expect to have a high Debye temperature, and which elements you would expect to have a low Debye temperature.

    The Debye temperature $T_d$ is defined through

    $$
    E_d = \hbar \omega_{d} = k_{\mathrm{B}} T_d
    $$

    and as was [shown in class](https://andy-utas.github.io/1-intoduction/1-2-specificheatII/#the-density-of-states), the Debye frequency is

    $$
    \omega_d^3 = 6\pi^2 n v_s^3
    $$

    where $v_s$ is the speed of sound in the material. Therefore, one would expect the materials with large $v_s$ to have the highest $T_d$. Consequently, a good guess for the highest $T_d$ would be diamond (and indeed, it is the highest). For low $T_d$, low speed of sound materials will be compressible - a small spring constant in the Einstein/Debye models - so the nobel gasses or soft metals (e.g. group I) would be good candidates.

## Exercise 3 - Sommerfeld

1. In your own words, explain what is the Fermi energy, Fermi temperature and the Fermi surface

    The Fermi energy is the chemical potential at $T=0$, the Fermi temperature is the associated temperature $T_F = E_F/k_{\textrm{B}}$, and is the temperature at which thermal energy would dictate the properties of a material to the same degree as the fact they are fermions. The Fermi surface is the surface in momentum space which separates the filled and unfilled states _at zero temperature__.

2. Write an expression for the number of states for a gas of free electrons in three dimension and use this to calculate the Fermi wavenumber and Fermi Energy

    $$
    N = \frac{2V}{(2\pi)^3} \int_{k<k_F} \mathrm{d}\mathbf{k}
    $$

    The factor of two is _very_ important. The integral is just the volume of a sphere of radius $k_F$, this is, $4\pi k_F^3/3$ which then yields

    $$
    k_F = (3\pi^2 N/V)^{1/3}
    $$

    and thus the Fermi energy is

    $$
    E_F = \frac{\hbar^2(3\pi^2 N/V)^{2/3}}{2m}
    $$

3. Using the previous result, estimate the value of the Fermi energy for Caesium

    Caesium has a density of $1.93\textrm{g/cm^3}$ and a mass of approximately $133 \textrm{amu}$  (132.9055) and thus the density of atoms is

    $$
    N/V = (1.93 \textrm{g/cm^3}) \times (10^2 \textrm{cm/m})^3 \times (\frac{1}{133}\textrm{mol/g}) \times (N_A \textrm{atoms/mol}) = 8.7 \textrm{atoms/m^3}
    $$

    and with one valence electron, $N/V$ for electrons is identical and we can plug it into the expression for $E_F$ from part (ii) which returns $E_F = 2.48 \times 10^{-19} \textrm {J} = 1.6 \textrm{eV}$

4. Obtain an expression for the density of states at the Fermi surface of a \textbf{two-dimensional} free-electron gas.

    For a two-dimensional gas

    $$
    N = 2A \int_{k<k_F} \frac{\mathrm{d}\mathbf{k}}{(2\pi)^2} = \frac{2A}{(2\pi)^2}\pi k_F^2
    $$

    where (again) $A$ is the area and the integral is over a circle with radius $k_F$ (c.f. exercise 1 (ii), only a factor of two different due to polarisation). Therefore

    $$
    k_F = (2\pi N/A)^{1/2}
    $$

    and the Fermi energy is

    $$
    E_F = \frac{\hbar^2 (2\pi N/A)}{2m} = \frac{\hbar^2\pi N/A}{m}
    $$

    The density of states is then independent of energy and is given by

    $$
    \frac{\mathrm{d}N}{\mathrm{d}E} = \frac{Am}{\hbar^2\pi} = N/E_F
    $$

5. Using the above result, show that for a two-dimensional free-electron gas that the chemical potential $\mu$ is independent of temperature when $T \ll \mu$

    From above, we have the density of states which we note to be temperature independent. Thus, for a fixed density of electrons, the chemical potential is fixed by

    $$
    n = \int_0^{\infty} \mathrm{d}E~g(E)~\frac{1}{\exp\left(\beta(E-\mu)\right)+1}.
    $$

    The connection one must make is that except for corrections exponentially small in $\beta\mu$, the value of the integral is independent of $\beta$ and thus one can assume that the dependence of $n$ on $\mu$ is temperature independent.

    If one wants to do the maths, we write the density of states as a constant $g$ (see above) and then the integral above can be recast

    $$
    n = g \int_{-\mu}^{\infty} \mathrm{d}x~\frac{1}{\exp(\beta x)+1} = g \int_{-\mu}^{\infty} \mathrm{d}x \frac{\exp(-\beta x)}{\exp(-\beta x)+1} = \frac{g}{\beta} \log(\exp(\beta \mu)+1)
    $$

    And for large $\beta\mu$ (small) we can expand to have

    $$
    n/g = \mu + \mathcal{O}\left(\exp(-\beta\mu)\right)
    $$

    which means that provided $T \ll \mu$, there is no dependence on the temperature.

## Exercise 4 - chemistry

1. Explain using the simplest language you can muster why is the periodic table important?

    Ability to predict properties of elements, ability to predict properties of compounds, ability to group/classify elements with similar characteristics, displays trends

2. Choose a naturally occurring element with a high atomic number and use Madelung's Rule to deduce the shell filling configuration.

    The configuration for uranium is shown below, and all shell filling will be in this order:

    U: 1s$^2$2s$^2$2p$^6$3s$^2$3p$^6$4s$^2$3d$^{10}$4p$^6$5s$^2$4d$^{10}$5p$^6$6s$^2$4e$^{14}$5d$^{10}$6p$^6$7s$^2$5f$^4$

    which can be written in shorthand as [Rn]7s$^2$5f$^4$.

3. Using any tools at your disposal (i.e. use a computer) produce a plot of the energy eigenstate described by $|5, 2, 0 \rangle$. You must include your code and you will be partially assessed on presentation: producing content that is digestible and visually pleasing is an important part of modern science!

    The electronic states of hydrogen can be found in many places (e.g. [Wikipedia](https://en.wikipedia.org/wiki/Hydrogen_atom)) and are given by

    $$
    \psi _{n\ell m}(r,\theta ,\varphi )={\sqrt {{\left({\frac {2}{na_{0}^{*}}}\right)}^{3}{\frac {(n-\ell -1)!}{2n(n+\ell )!}}}}e^{-\rho /2}\rho ^{\ell }L_{n-\ell -1}^{2\ell +1}(\rho )Y_{\ell }^{m}(\theta ,\varphi )
    $$

    where $\rho = 2r/n a_0^*$, $a_0^*=4\pi\epsilon_0\hbar^2/\mu e^2$ is the reduced Bohr radius, $\mu = m_e M/(m_e + M)$ is the reduced mass, $L_{n-\ell -1}^{2\ell +1}(\rho )$ is the generalised Laguerre polynomial and $Y_{\ell }^{m}(\theta ,\varphi )$ is the spherical harmonic function.

## Exercise 5 - Bonding: not LCAO

1. In you own words, explain why ionic bonds occur, and what properties one would expect from and ionic solid.

    Ionic bonds occur as an electron is transferred from one atom to another, and the resulting ions attract each other. Typical properties are due to the nature of the bond being very strong, with materials having high melting temperatures, and usually being hard, brittle, and electrically insulating. They are also mostly soluble, but this is not of so much relevance here.

2. The (first) ionisation energy of sodium is roughly $5.14\mathrm{eV}$, and the electron affinity of chlorine is roughly $3.62\mathrm{eV}$, and the bond length between the two atoms when a sodium chloride molecule is formed is roughly $0.236\mathrm{nm}$. Assuming that _all_ of the cohesive energy is due to the Coulomb interaction, calculate the bonding energy.

    The cohesive energy is related to the bond distance $d$ via

    $$
    E_{coh} = \frac{e^2}{4\pi\epsilon_0 d}.
    $$

    Using the value $d= 2.36 \unicode{x212B}$ one finds a cohesive enrgy of $6.10\mathrm{eV}$ and thus the total binding energy is

    $$
    E = -5.14 + 3.62 + 6.10 = 4.58 \mathrm{eV}
    $$

3. The measured value of the bonding energy of sodium chloride is $4.26\mathrm{eV}$. How does this compare to your value above? Justify your response.

    The calculated value above is slightly larger than the measured value with the reason for the discrepancy being there must be a repulsive fore between the ions (otherwise the would collapse into a singularity!) in addition to the Coulomb attraction, therefore reducing the size of the cohesive (binding) energy.

4. In our discussion of bonding, we did not explicitly discuss van der Waals bonding. Research what is the nature of the van der Waals bond, explicitly describing the origin of the attractive force formation and reason as to why the force is of the form $R^{-7}$

    Van der Waals forces are from correlated dipole fluctuations. If the electron is a given fixed position, there is a dipole moment $\mathbf{p} = e\mathbf{r}$ where $\mathbf{r}$ is the vector from the electron to the proton. With the electron "orbiting" (i.e, in an eigenstate), the average dipole moment is zero. However, if an electric field is applied to the atom, the atom will develop a polarisation (i.e., it will be more likely for the electron to be found on one side of the nucleus than on the other). We write

    $$
    \mathbf{p} = \chi \mathbf{E}
    $$

    with $\chi$ the polarisability. Now, let us suppose we have two such atoms, separated a distance $r$ in the $\hat{x}$ direction. Suppose one atom momentarily has a dipole moment $\mathbf{p}_1$ (for definiteness, suppose this dipole moment is in the $\hat{z}$ direction). Then the second atom will feel an electric field

    $$
    E = \frac{p_1}{4\pi\epsilon_0 r^3}
    $$

    in the negative $\hat{z}$ direction. The second atom then, due to its polarisability, develops a dipole moment $p_2 = \chi E$ which in turn is attracted to the first atom. The potential energy between these two dipoles is

    $$
    U=\frac{-\left|p_{1}\right|\left|p_{2}\right|}{4 \pi \epsilon_{0} r^{3}}=\frac{-p_{1} \chi E}{\left(4 \pi \epsilon_{0}\right) r^{3}}=\frac{-\left|p_{1}\right|^{2} \chi}{\left(4 \pi \epsilon_{0} r^{3}\right)^{2}}
    $$

    corresponding to a force which is attractive and proportional to $1/r7$. Note that while for a single isolated atom $\langle p \rangle = 0$ the result is proportional instead to $\langle |p|^2 \rangle \sim \langle |r|^2 \rangle$ with r the position of an electron, is nonzero.

## Exercise 6 - Bonding: LCAO

In our formulation of the LCAO formulation we assumed that orbitals were orthogonal, with the justification that the qualitative behaviour was still going to be fine.

Assume that we introduce a trial wavefunction:

\[
|\psi \rangle = \sum_{i=1}^{N} \phi_i |i\rangle
\]

however, we are not going to enforce that the state be orthogonal. Rather, we define an overlap matrix $\mathcal{S}$ with elements

\[
\mathcal{S}_{i,j} = \langle i | j \rangle
\]

1. Show that with the above conditions, one arrives at an _effective_ Schrödinger equation

    \[
    \mathcal{H} \phi = E\mathcal{S}\phi
    \]

    where

    \[
    \mathcal{H}_{i,j} = \langle i | \hat{H} | j \rangle
    \]

    and $\phi$ is the vector of the coefficients for the $\phi_i$.

    This is the variational method 101. It is necessary to compute $E$ through

    $$
    E=\frac{\langle\psi|H| \psi\rangle}{\langle\psi \mid \psi\rangle}=\frac{\sum_{n, m} \phi_{n}^{*} \mathcal{H}_{n m} \phi_{m}}{\sum_{n, m} \phi_{n}^{*} S_{n m} \phi_{m}}
    $$

    which must then be minimised with respect to the $\phi_n$. This is most simply done by differentiating with respect to $\phi_n^*$ and solving for the root(s):

    $$
    \begin{aligned}
    0 =\frac{\partial E}{\partial \phi_{n}^{*}} & =\frac{\sum_{m} \mathcal{H}_{n m} \phi_{m}}{\sum_{n, m} \phi_{n}^{*} S_{n m} \phi_{m}}-\left(\frac{\sum_{n, m} \phi_{n}^{*} \mathcal{H}_{n m} \phi_{m}}{\sum_{n, m} \phi_{n}^{*} S_{n m} \phi_{m}}\right) \frac{\sum_{n, m} S_{n m} \phi_{m}}{\sum_{n, m} \phi_{n}^{*} S_{n m} \phi_{m}} \\
    & =\sum_{m} \mathcal{H}_{n m} \phi_{m}-E \sum_{m} S_{n m} \phi_{m}
    \end{aligned}
    $$

    where we have used the definition of $E$ above to simplify the 2nd term in the top line. This is exactly the result required.

2. Consider the case where N=2 (i.e. the diatomic case) and the orbitals are $s$ ($l=0$) orbitals. Use the above equation to solve for the energy eigenvalues of the system.

    Firstly, the reason we consider $s$ states is because an $s$ orbital can be taken to be manifestly positive everywhere (it has no nodes), so overlaps $S_{ij}$ must be real and positive, making life a little easier.

    In order to solve the equation

    \[
    \mathcal{H} \phi = E\mathcal{S}\phi
    \]

    it is simplest to solve the eigenvalue problem

    \[
    \mathcal{S}^{-1}\mathcal{H} \phi = E\phi.
    \]

    As we normally do, we write the Hamiltonian $\mathcal{H}$ as

    $$
    \mathcal{H}=\left(\begin{array}{cc}
    \epsilon & t \\
    t^{*} & \epsilon
    \end{array}\right)
    $$

    with $t$ the hopping and $\epsilon = \epsilon_0 + V_{\mathrm{cross}}$, and the overlap matrix is just

    $$
    \mathcal{S}=\left(\begin{array}{cc}
    1 & S \\
    S & 1
    \end{array}\right)
    $$

    where we have defined the only non-trivial element $\mathcal{S}_{12} = S$. We then need to diagonalise

    $$
    \mathcal{S}^{-1} \mathcal{H}=\frac{1}{1-S^{2}}\left(\begin{array}{cc}
    \epsilon-S t & t-\epsilon S \\
    t-\epsilon S & \epsilon-S t
    \end{array}\right)
    $$

    which has eigenvalues

    \begin{equation}
    E_{\pm} = \frac{1}{1-S^2}\left( |\epsilon - S t| \pm |t - \epsilon S| \right).
    \end{equation}

## Exercise 4 - One-dimensional oscillations

1. Explain what is meant by a _normal mode_ and a _phonon_

    A _normal mode_ is a periodic collective motion where all particles move at the same frequency. A _phonon_ is a quantum of vibration.

    People tend to be confused by phonons, so to explicitly connect the two and explain why phonons are bosons: each classical normal mode of vibration corresponds to a quantum mode of vibration which can be excited multiple times. A single mode may be occupied by a single phonon, or it may be occupied with multiple phonons corresponding to a larger amplitude oscillation. The fact that the same state may be multiply occupied by phonons means that phonons must be bosons.

2. Derive the dispersion relation for longitudinal oscillations of an infinite one-dimensional chain of identical atoms, assuming mass $m$, spring constant $\kappa$, and lattice spacing $a$

    The equation of motion of the $n^{\textrm{th}}$ particle along the chain is given by

    $$
    m \ddot{x}_{n}=\kappa\left(x_{n+1}-x_{n}\right)+\kappa\left(x_{n-1}-x_{n}\right)=\kappa\left(x_{n+1}+x_{n-1}-2 x_{n}\right)
    $$

    where $na$ is the equilibrium position of the $n^{\textrm{th}}$ particle. Looking for solutions of the form

    $$
    x_n = A e^{i\omega t - i k n a}
    $$

    one obtains

    $$
    \begin{aligned}
    -\omega^{2} m e^{i \omega t-i k n a} &=\kappa e^{i \omega t}\left(e^{i k(n+1) a}+e^{i k(n-1) a}-2 e^{i k n}\right) \\
    \omega^{2} m &=2 \kappa(\cos (k a)-1)
    \end{aligned}
    $$

    which can be recast as

    $$
    \omega = \sqrt{\frac{2\kappa}{m}\left(\cos(ka)-1\right)} = 2\sqrt{\frac{\kappa}{m}}\left|\sin\left(\frac{ka}{2}\right)\right|
    $$

3. Show that a the mode with wavevector $k$ is equivalent to the mode $k + 2\pi/a$

    $$
    e^{-i(k+2\pi/a)na} = e^{-i k n a} e^{-i 2\pi n} = e^{-i k n a}
    $$

4. Assuming periodic boundary conditions, how many different modes are there?

    If one assumes periodic boundary conditions, then $k = 2 \pi m/L$, but $k$ is identified with $k + 2 \pi /a$ so that there are therefore exactly $N = L/a$ different normal modes.

5. Find expressions for and plot both the group and phase velocities

    The phase velocity is calculated via

    $$
    v_p = \omega/k = \frac{2\sqrt{\frac{\kappa}{m}}\left|\sin\left( \frac{ka}{2} \right)\right|}{k}
    $$

    and the group velocity is

    $$
    v_g = \frac{d\omega}{dk} = a\sqrt{\frac{\kappa}{m}} \cos\left(\frac{|k|a}{2}\right) = \frac{a \omega_0}{2}\sqrt{1-\frac{\omega^2}{\omega_0^2}}
    $$

    where $\omega_0 = 2\sqrt{\kappa/m}$.

    To plot this, code such as that below

    ``` python
    kappa = 1
    m = 1
    a = 1

    def omega(k):
       return 2 * np.sqrt(kappa/m) * abs(np.sin(k * a / 2))

    def v_p(k):
       return omega(k)/k

    def v_g(k):
       omega_0 = 2 * np.sqrt(kappa/m)
       return omega_0 * (a/2) * np.sqrt(1 - (omega(k)/omega_0) ** 2)

    fig, ax = plt.subplots()
    k = np.linspace(-np.pi+0.01, np.pi-0.01, 300)

    ax.plot(k[0:149], v_p(k[0:149]), color = 'C0', label = 'Phase velocity');
    ax.plot(k[150:300], v_p(k[150:300]), color = 'C0');
    ax.plot(k[0:149], -v_g(k[0:149]), color = 'C1', label = 'Group velocity');
    ax.plot(k[150:300], v_g(k[150:300]), color = 'C1');
    ax.set_title('Velocities')
    ax.set_xlabel(r'$k$');
    ax.set_ylabel('$v(k)$');
    plt.xticks([-np.pi, 0, np.pi], [r'$-\pi/a$', 0, r'$\pi/a$']);
    plt.yticks([-1, 0, 1], [r'$-2\sqrt{\frac{\kappa}{m}}$', 0, r'$2\sqrt{\frac{\kappa}{m}}$']);
    plt.legend();
    plt.tight_layout();

    plt.savefig('A2-4-v.pdf', facecolor='white', transparent=False)

    plt.show()
    ```

    will yield this plot:

    ![](../images/A2-4-v.svg)

6. Find an expression for the density of states $g(\omega)$ and plot $g(\omega)$

    The density of states is uniform in $k$: if there are $N$ sites in the system, there are $N$ modes total and the density of states is therefore $dN/dk = Na/(2\pi) = L/(2\pi)$ where $L$ is the length of the system. We then have

    $$
    \begin{aligned}
    g(\omega) &=d N / d \omega=(d N / d k)(d k / d \omega)=\frac{N a}{2 \pi v_{\text {group }}} \\
    &=\frac{N}{2 \pi \sqrt{\kappa / m} \cos (|k| a / 2)} \\
    &=\frac{2 N}{2 \pi \sqrt{(\kappa / m)-(\omega(k) / 2)^{2}}}
    \end{aligned}
    $$

    where we have used

    $$
    \left(\frac{\omega}{2}\right)^2 + \left(\frac{v_g}{a}\right)^2 = \frac{\kappa}{m}
    $$

    where in turn we have used the equation for the group velocity (previous question) to obtain the above identity.

    Note that the additional factor of 2 that appears in the numerator is to account for the fact that for each value of $\omega > 0$ there are actually two values of $k$ with that $\omega$, to ensure that if you integrate over frequency you correctly get back $N$ degrees of freedom.

    ![](../images/A2-4-dos.svg)

    The above plot was produced using the code below

    ``` python
    N = 1
    fig, ax = plt.subplots()
    w = np.linspace(0, np.pi/a - 1.15, 300);
    g = (2*N)/(2 * np.pi * np.sqrt((kappa/m)-(w/2)**2));
    ax.plot(w, g, 'C0');
    ax.set_xlabel(r'$\omega$');
    ax.set_ylabel('$g(\omega) [N/(\pi \sqrt{k/m})]$');
    ax.set_title('Density of states')
    plt.yticks([N/(np.pi * np.sqrt(kappa/m)), 2, 3], [1, 2, 3]);
    ax.set_ylim(0,3)
    plt.tight_layout();
    plt.savefig('A2-4-dos.pdf', facecolor='white', transparent=False)
    plt.show()
    ```  

7. Using $g(\omega)$, find an expression for the heat capacity and use any tools at your disposal to plot the heat capacity versus temperature

    The energy stored in the chain is given by

    $$
    U = \int d\omega~g(\omega)~\hbar \omega \left(n_{\textrm{B}}(\omega)+1/2\right)
    $$

    and so the heat capacity is $\partial U/\partial T$. The factor of 1/2 can be ignored as it is a temperature independent constant and thus will vanish upon differentiation.

    Plotting this requires numerical integration of the above equation, and one should get a plot similar to that as shown below, with the values on the $x$ axis changing with the parameters $\kappa$, $m$, and $a$.

    Code to perform the numerical integration appears below, with the highlighted lines actually performing the integration

    ``` python hl_lines="9-16"
    a = 1e-10

    def integrand(w):
      b = 1/T
      nb = 1/(np.exp(b * w) - 1)
      g = (2*N)/(2 * np.pi * np.sqrt((kappa/m)-(w/2)**2))
      return g * w * nb

    temp = np.linspace(0.01, 5, 150)
    U = []

    for T in temp:
      U.append(integrate.quad(integrand, 0, 2*np.sqrt(kappa/m))[0])

    dt = temp[1]-temp[0]
    dudt = np.gradient(U, dt)

    fig, ax = plt.subplots()
    ax.plot(temp, dudt)
    ax.set_xlabel('$T$ [K]')
    ax.set_ylabel('$C/k_\mathrm{B}$')
    ax.set_title('Specific heat')
    plt.savefig('A2-4-c.pdf', facecolor='white', transparent=False)
    plt.show()
    ```

    the output of which is shown here:

    ![](../images/A2-4-c.svg)