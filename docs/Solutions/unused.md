## Exercise 2 - Drude: mixed ion-electron conductors (MIECs)

1. Calculate the electrical resistivity $\rho$

    Assuming that both species respond to the electric field independently - we assume that there are no interactions - the total conductivity is the sum of the two independent conductivities

    $$
    \sigma = \sigma_e + \sigma_i = e^2 \left(\frac{n_e \tau_e}{m_e} + \frac{n_i \tau_i}{m_i}\right)
    $$

    and therefore the resistivity $\rho = 1/\sigma$

    $$
    \rho  \frac{1}{e^2 \left(\frac{n_e \tau_e}{m_e} + \frac{n_i \tau_i}{m_i}\right)}
    $$

2. Calculate the thermal conductivity $\kappa$

    The thermal conductivity is calculated in the same way as the resistivity, in that we add the two pieces:

    $$
    \kappa = \kappa_e + \kappa_i = \frac{4k_{\textrm{B}}^2 T}{\pi} \left( \frac{n_e \tau_e}{m_e} + \frac{n_i \tau_i}{m_i} \right)
    $$

3. What is the Wiedemann-Franz law? Does it hold in this situation?

    The Wiedemann-Franz law states that the ratio (also known as the Lorenz number)

    $$
    L = \frac{\kappa}{T\sigma} = \frac{3}{2} \left(\frac{k_{\textrm{B}}}{e}\right)
    $$

    is roughly constant for metals, and it indeed holds for MIECs

4. If we consider a magnetic field applied in the $+z$ direction, we need only consider the conductivity in $x$ and $y$ and can write

    $$
    \rho =
    \begin{pmatrix}
    \frac{m}{nq^2\tau} & \frac{Bq}{n} \\
    -\frac{Bq}{n} & \frac{m}{nq^2\tau}
    \end{pmatrix}
    $$

    which is true for both charge carrier species. Use this result to calculate the resistivity matrix in the case of a MIEC.

    To make life simpler, one can write

    $$
    \rho =
    \begin{pmatrix}
    r & B R \\
    -B R & r
    \end{pmatrix}
    $$

    where $r = m/(n q^2 \tau)$ and $R=q/n$. We can then define $\rho_e$ and $\rho_i$ for the two species. The conductivities are then $\sigma_j=\rho_j^{-1}$ for $j = e, i$, and then the total conductivity $\sigma_t = \sigma_e + \sigma_i$. The total resistivity is then $\rho = \sigma_t^{-1}$ \mrk{1}. The process is pretty algebra heavy, but the results are

    \begin{align}
    \rho_{xx} & = \frac{B^2 (r_e R_i^2 + r_i R_e^2) + r_i r_e (r_e + r_i)}{B^2 (R_e + R_i)^2 + (r_e + r_i)^2} \\
    \rho_{xy} & = \frac{B (B^2 R_e R_i (R_e + R_i) + R_i r_e^2 + R_e r_i^2 }{B^2 (R_e + R_i)^2 + (r_e + r_i)^2}
    \end{align}

    Note that using software to do this kind of grunt work is absolutely fine (encouraged even)

## Exercise 3 - Quantum thermal expansion

In a _content unpacking_ session, we discussed thermal expansion arising from the anharmonic term in the interatomic potential. Assume masses $m_1$ and $m_2$ for the interacting particles and let's consider an anharmonic perturbation $\delta V$

\[
\delta V = -\frac{\kappa_3}{6}(x-x_0)^3
\]

to the one-dimensional quantum harmonic oscillator $H_0$:

\[
H_0 = \frac{p^2}{2m}+\frac{\kappa}{2}(x-x_0)^2.
\]

To first order in $\kappa_3$, it can be shown that

\[
\langle n | x | n \rangle = x_0 + \frac{E_n \kappa_3}{2\kappa^2}
\]

where $|n\rangle$ is the eigenstate of the harmonic oscillator with

\[
E_n = \hbar\omega \left(n+\frac{1}{2}\right)
\]

1. What is the value of $\omega$ in terms of $m_1$ and $m_2$?

    The relationship between frequency and mass for a harmonic oscillator is

    $$
    \omega = \sqrt{\frac{\kappa}{m}}
    $$

    and given our system is comprised of two masses $m_1$ and $m_2$, we should use the _reduced_ mass $\mu$:

    $$
    \mu = \frac{m_1 m_2}{m_1 + m_2}
    $$

2. What is the interpretation of the $|0\rangle$ state?

    The $|0\rangle$ state is the ground state of the harmonic oscillator, which has some notable features, but most relevant is that the energy is not equal to the minimum of the potential, but rather $\hbar\omega/2$ above the minimum, and therefore the will be fluctuations in both the position and momentum of the trapped particle around the minimum which is what gives rise to the average separation of atoms.


3. The expectation value of $x$ as a function of temperature is written as

    \[
    \langle x \rangle_{\beta} = \frac{\sum_n \langle n | x | n \rangle e^{-\beta E_n}}{\sum_n e^{-\beta E_n}}
    \]

    1. Find the coefficient of thermal expansion

        Just crank the handle:

        $$
        \begin{aligned}
        \langle x\rangle_{\beta} &=\frac{\sum_{n}\langle n|x| n\rangle e^{-\beta E_{n}}}{\sum_{n} e^{-\beta E_{n}}}=\frac{\sum_{n} \left(x_{0}+E_{n} \kappa_{3} /\left(2 \kappa^{2}\right) \right) e^{-\beta E_{n}}}{\sum_{n} e^{-\beta E_{n}}} \\
        &=x_{0}+\frac{\langle E\rangle_{\beta} \kappa_{3}}{2 \kappa^{2}}
        \end{aligned}
        $$

        where $\langle E \rangle_\beta$ is the energy expectation of a harmonic oscillator of frequency $\omega$ at temperature $\beta = 1/(k_{\mathrm{B}} T)$. It is fine to use the result that  $\langle E \rangle_\beta$ directly:

        $$
        \begin{aligned}
        \langle E\rangle_\beta &=-(1 / Z) \partial Z / \partial \beta=(\hbar \omega / 2) \operatorname{coth}(\beta \hbar \omega / 2) \\
        &=\hbar \omega\left(n_{B}(\beta \hbar \omega)+\frac{1}{2}\right)
        \end{aligned}
        $$

        but this can be derived easily enough from the partition function:

        $$
        \begin{aligned}
        Z_{1 d} &=\sum_{n \geq 0} e^{-\beta \hbar \omega(n+1 / 2)} \\
        &=e^{-\beta \hbar \omega / 2} 1 /\left(1-e^{-\beta \hbar \omega}\right) \\
        &=1 /[2 \sinh (\beta \hbar \omega / 2)]
        \end{aligned}
        $$

        Combining the above equations one arrives at

        $$
        \langle x\rangle_{\beta}=x_{0}+\left(\kappa_{3} \hbar \omega /\left(4 \kappa^{2}\right)\right) \operatorname{coth}(\beta \hbar \omega / 2)
        $$

        and then the coefficient of thermal expansion is then

        $$
        \alpha=\frac{1}{x_{0}} \frac{d\langle x\rangle_{\beta}}{d T}=\frac{\kappa_{3}}{2 x_{0} \kappa^{2}} \frac{d\langle E\rangle}{d T}
        $$

        The term $\frac{d\langle E\rangle}{d T}$ is identified as the specific heat $C$, and the specific heat of the a harmonic oscillator was covered when discussing the Einstein model of a solid, but can be calculated directly from the equation for $\langle E \rangle_\beta$ to yield

        \begin{equation}
        \alpha=\frac{\kappa_{3} C}{2 x_{0} \kappa^{2}}=\frac{\kappa_{3}}{2 x_{0} \kappa^{2}} k_{b}(\beta \hbar \omega)^{2} \frac{e^{\beta \hbar \omega}}{\left(e^{\beta \hbar  \omega}-1\right)^{2}}
        \end{equation}


    2. What is the behaviour of the coefficient at both high and low temperature, and comment on the physical significance of these results.

    In the low-temperature limit, the modes "freeze" out, entirely analogous to the specific heat dropping out at low temperature (there needs to be a minimum energy put into the system to enact change because of the quantised states of the harmonic oscillator).

    In the high-temperature limit, $C \rightarrow k_{\mathrm{B}}$ so one obtains

    $$
    \alpha = \frac{\kappa_3 k_{\mathrm{B}}}{2 x_0 \kappa^2}
    $$

    in agreement with the classical result, and this result is valid when $k_{\mathrm{B}} T \gg \hbar \omega.$

## Exercise 3 - Filing factor

    Consider a lattice with a sphere at each lattice point, and choose the radius of the spheres to be such that neighbouring spheres just touch. The filling factor (or packing fraction) is the fraction of the volume of all of space which is enclosed by the union of all the spheres (i.e. the ratio of the volume of the spheres to the total volume).

    1. Calculate the packing fraction for a simple cubic lattice

        The volume of a conventional unit cell is $V = a^3$. Each cell corresponds to a single sphere, and the radius of this sphere is $a/2$ so the volume of the sphere is $V_s = 4\pi/3 \times (a/2)^3$. Therefore the packing fraction $V_s/V = \pi/6 \approx 0.52$

    2. Calculate the packing fraction for a BCC lattice

        The volume of a conventional unit cell is $V = a^3$. Each conventional cell contains two lattice points which are a distance $a\sqrt{3}/2$ apart, thus the radius of each sphere is $a\sqrt{3}/4$ so the volume of the sphere is $V_s = 4\pi/3 \times (a\sqrt{3}/4)^3$. Therefore the packing fraction $2V_s/V = \pi\sqrt{3}/8 \approx 0.68$

    3. Calculate the packing fraction for an FCC lattice

        The volume of a conventional unit cell is $V = a^3$. Each conventional cell contains four lattice points which are a distance $a\sqrt{2}/2$ apart, thus the radius of each sphere is $a\sqrt{2}/4$ so the volume of the sphere is $V_s = 4\pi/3 \times (a\sqrt{2}/4)^3$. Therefore the packing fraction $4V_s/V = \pi/(3\sqrt{2}) \approx 0.74$

## Exercise 4 - Reciprocal lattice  

    1. Show that the reciprocal lattice of a FCC lattice is a BCC lattice. Correspondingly, show that the reciprocal lattice of a BCC lattice is an FCC lattice

        The BCC has primitive lattice vectors

        $$
        \begin{aligned}
        &\mathbf{a}_{1}=[1,0,0] ~ a \\
        &\mathbf{a}_{2}=[0,1,0] ~ a \\
        &\mathbf{a}_{3}=[1 / 2,1 / 2,1 / 2] ~ a
        \end{aligned}
        $$

        from which we can construct primitive lattice vectors for the reciprocal lattice via

        $$
        \mathbf{b}_{i}=\frac{2 \pi \mathbf{a}_{j} \times \mathbf{a}_{k}}{\mathbf{a}_{1} \cdot \mathbf{a}_{2} \times \mathbf{a}_{3}}
        $$

        which gives

        \begin{equation}
        \begin{aligned}
        \mathbf{b}_{1} &= (1 / 2,0,-1 / 2) ~ \frac{4 \pi}{a} \\
        \mathbf{b}_{2} &= (0,1 / 2,-1 / 2) ~ \frac{4 \pi}{a} \\
        \mathbf{b}_{3} &= (0,0,1) ~ \frac{4 \pi}{a}
        \end{aligned}
        \end{equation}

        and they themselves can be transformed into the standard PLVs via

        $$
        \begin{aligned}
        \mathbf{b}_{1}^{\prime} &=\mathbf{b}_{1}+\mathbf{b}_{3} & = &(1 / 2,0,1 / 2) ~ \frac{4 \pi}{a} \\
        \mathbf{b}_{2}^{\prime} &=\mathbf{b}_{2}+\mathbf{b}_{3} & = &(0,1 / 2,1 / 2) ~ \frac{4 \pi}{a} \\
        \mathbf{b}_{3}^{\prime} &=\mathbf{b}_{1}+\mathbf{b}_{2}+\mathbf{b}_{3} & = &(1 / 2,1 / 2,0) ~ \frac{4 \pi}{a}
        \end{aligned}
        $$

        which is fine since we are making integer additions of PLVs.

    2. If an FCC lattice has conventional unit cell with lattice constant $a$, what is the lattice constant for the conventional unit cell of the reciprocal BCC lattice?

        From above, we can see that the lattice constant is $4\pi/a$

    3. Consider now an orthorhombic face-centred lattice with conventional lattice constants $a_1, a_2, a_3$. What is the reciprocal lattice now?

        Everything from above still holds, except one would have basis vectors scaled to $4\pi/a_i$

## Exercise 4 - Diffraction and structure

    1. Compute the structure factor $S$ of the BCC lattice

        The structure factor $S(\mathbf{G})$ is given by

        $$
        \sum_j f_j e^{i\mathbf{G} \cdot \mathbf{r}_j}
        $$

        where the sum over $j$ is the atoms in the unit cell. We can write this explicitly as

        $$
        \sum_j f_j e^{2\pi i hu_j + kv_j + lw_j} f_j
        $$

        where $(hkl)$ are the miller indices of $\mathbf{G}$ and $[u_j, v_j, w_j]$ are the positions of atom $j$ in the unit cell. To compute this, we write a BCC lattice as a simple cubic with a basis [0,0,0] and [1/2, 1/2, 1/2], and therefore we get the structure factor

        $$
        \begin{align}
        S & = f_{\textrm{Cr}} + f_{\textrm{Cr}} e^{2\pi i(h/2 + k/2 + l/2)} \\
        & = f_{\textrm{Cr}}\left(1 + (-1)^{h+k+l}\right)
        \end{align}
        $$

    2. Which diffraction peaks are missing?

        From above, it is clear that the structure vanishes whenever $h+k+l$ is odd, and we can write

        $$
        S = \left\{ \begin{array}{ll} 2f_{\textrm{Cr}} \quad h+k+l~\textrm{even} \\ 0 \quad h+k+l~\textrm{odd} \end{array} \right.
        $$

    3. How does this structure factor change if the atoms in the centre of the conventional unit cell have a different form factor from the atoms at the corner of the conventional unit cell?

        If we write the atomic form factors of the different atoms $f_1$ and $f_2$

        $$
        S = \left\{ \begin{array}{ll} f_1 + f_2 \quad h+k+l~\textrm{even} \\ f_1 - f_2 \quad h+k+l~\textrm{odd} \end{array} \right.
        $$

    4. A student carried out X-ray powder diffraction on chromium (Cr) which is known to have a BCC structure, and the first five diffraction peaks are given below. Delightfully, the student took the liberty of assigning Miller indices to the peaks. Were the peaks assigned correctly? Fix any mistakes and explain your reasoning.
    ![](../images/A5-Cr.svg)

        The values of $(hkl)$ must satisfy the selection rules above, which means that the peaks should be $(110), (200), (211), (220), (310)$ from lowest angle to highest angle.

    5. The X-ray diffraction was carried out using Cu $K_\alpha$ radiation ($\lambda = 1.5406 \mathrm{\unicode{x212B}}$). Use this information to calculate the lattice constant $a$ of the chromium BCC unit cell, and provide an estimate for uncertainty of this value.

        To calculate the lattice spacing, one must use the relations that for a given lattice spacing $d_{(h,k,l)}$, the Bragg condition holds:

        $$
        d_{(h,k,l)} = \frac{\lambda}{2 \sin\theta}
        $$

        In a cubic lattice, one also has the relation that

        $$
        d_{(h,k,l)} = \frac{a}{\sqrt{h^2 + k^2 + l^2}}
        $$

        so then the lattice constant $a$ can be calculated through

        $$
        a = \frac{\lambda\sqrt{h^2 + k^2 + l^2}}{2 \sin\theta}
        $$

        One can the calculate a value for each angle (and Miller index) to return a list of lattice constants, from which a range an uncertainty can be derived. I have just used the mean and standard deviation - no weighted means, no uncertainty in peak location, just raw statistical deviation from my _very_ rough extraction of the scattering angle.

        ``` python
        lamb = 1.5406 #[\unicode{x212B}]
        def lat(h, k, l, t):
          return (np.sqrt(h**2 + k**2 + l**2) * lamb)/(2*np.sin(t))

        angles = np.array([44, 63, 81, 97, 113])
        miller = np.array([[1,1,0], [2,0,0], [2,1,1], [2,2,0], [3,1,0]])

        touse = []
        for (n, p) in enumerate(miller):
          touse.append(np.append(p, np.deg2rad(angles[n]/2)))

        avals = []
        for d in touse:
          avals.append(lat(*d))

        print(f"The lattice spacing was determined to be {np.mean(avals):.3f} with a standard deviation of {np.std(avals):.3f}")
        ```

        My result was $a = 2.918 \pm 0.016 \mathrm{\unicode{x212B}}$

## Exercise 3 - Fermi surfaces

Consider a tight binding model of atoms on a (two-dimensional) square lattice where each atom has a single atomic orbital.

1. If these atoms are monovalent, describe the shape of the Fermi surface.

    The dispersion of the tight binding model is given by

    $$
    \epsilon_{k_x, k_y} = -2t \left( \cos(k_x a) + \cos(k_y a) \right)
    $$

    and a plot of the dispersion is shown below

    ![](../images/A6-3-tightbindingdisp.svg)

    ??? example "Fermi surface code"

        ``` python
        from matplotlib import cm
        from mpl_toolkits.mplot3d import Axes3D
        # Axes3D import has side effects, it enables using projection='3d' in add_subplot

        a = 1
        t = 2

        def ep(kx, ky):
            return -2*t * (np.cos(kx*a) + np.cos(ky*a))

        fig = plt.figure()
        ax = fig.add_subplot(111, projection='3d')
        x = y = np.arange(-np.pi/a, np.pi/a, 0.05)
        X, Y = np.meshgrid(x, y)
        zs = np.array(ep(np.ravel(X), np.ravel(Y)))
        Z = zs.reshape(X.shape)

        surf = ax.plot_surface(X, Y, Z, cmap=cm.coolwarm)

        ax.set_xlabel(r'$k_x$')
        ax.set_ylabel(r'$k_y$')
        ax.set_zlabel(r'$\epsilon$')

        fig.colorbar(surf, shrink=0.5, aspect=5)  

        if True:
            plt.savefig('A-6-3-tightbindingdisp.svg', facecolor='white', transparent=False, bbox_inches='tight')

        plt.show()
        ```

    which although it looks cool, it is much more useful to look at a contour plot of the energy:

    ![](../images/A6-3-tightbindingcontour.svg)

    ??? example "Contour plot code"

        ``` python
        fig,ax=plt.subplots(1,1)
        x = y = np.arange(-np.pi/a, np.pi/a, 0.05)

        zs = np.array(ep(np.ravel(X), np.ravel(Y)))
        Z = zs.reshape(X.shape)

        cp = ax.contourf(X, Y, Z, 11, cmap=cm.coolwarm)
        fig.colorbar(cp) # Add a colorbar to a plot
        ax.set_title('Tight binding model dispersion')
        ax.set_xlabel('$k_x$')
        ax.set_ylabel('$k_y$')

        if True:
            plt.savefig('A-6-3-tightbindingcontour.svg', facecolor='white', transparent=False, bbox_inches='tight')

        plt.show()
        ```

    If we are considering a monovalent unit cell, then the Brillouin zone is half filled:

    ![](../images/A6-3-tightbindingmonovalent.svg)

    ??? example "Filled cell code"

        ``` python
        fig,ax=plt.subplots(1,1)
        x = y = np.arange(-np.pi/a, np.pi/a, 0.1)

        zs = np.array(ep(np.ravel(X), np.ravel(Y)))
        Z = zs.reshape(X.shape)

        maxfilled = np.sort(zs)[int(len(zs)/2)]
        for z in Z:
            z[z>round(maxfilled)] = None

        cp = ax.contourf(X, Y, Z, 11, cmap='binary')
        fig.colorbar(cp) # Add a colorbar to a plot
        ax.set_title('Monovalent tight binding system')
        ax.set_xlabel('$k_x$')
        ax.set_ylabel('$k_y$')

        if True:
            plt.savefig('A-6-3-tightbindingmonovalent.svg', facecolor='white', transparent=False, bbox_inches='tight')

        plt.show()
        ```

2. Now suppose the lattice is not square, but is instead rectangular with primitive lattice vectors of length $a_x$ and $a_y$ in the $x$ and $y$ directions respectively, where $a_x > a_y$. Imagine that the hopping have a value $-t_x$ in the $x-$direction and a value $-t_y$ in the $y-$direction, with $t_y > t_x$.

    1. Given that $a_x > a_y$, why would one expect $t_y > t_x$?

        If $a_x > a_y$ one expects the hopping magnitude to be smaller in the $x$ direction since the atoms are further apart (although this is not holy, as the orbitals, such as $p_x$ orbitals, may not be isotropic).

    2. Write an expression for the dispersion of the electronic states $\epsilon(\mathbf{k})$

        Basically the same as above, but with anisotropy:

        $$
        \epsilon_{k_x, k_y} = -2t_x \cos(k_x a_y) - 2t_y \cos(k_y a_y)
        $$

    3. Suppose once again that the atoms are monovalent. What is the shape of the Fermi surface?

        As an example, let us choose $t_y = 3t_x$ but $a_x = ay = a$ for simplicity. A contour plot of this energy is given shown below:

        ![](../images/A6-3-tightbindingcontour_noniso.svg)

        ??? example "Contour plot code"

            ``` python
            a = 1
            t_x = 2
            t_y = 2 * t_x

            def ep(kx, ky):
                return -2*t_x*np.cos(kx*a) - 2*t_y*np.cos(ky*a)

            fig,ax=plt.subplots(1,1)
            x = y = np.arange(-np.pi/a, np.pi/a, 0.05)

            zs = np.array(ep(np.ravel(X), np.ravel(Y)))
            Z = zs.reshape(X.shape)

            cp = ax.contourf(X, Y, Z, 11, cmap=cm.coolwarm)
            fig.colorbar(cp) # Add a colorbar to a plot
            ax.set_title('Tight binding model dispersion')
            ax.set_xlabel('$k_x$')
            ax.set_ylabel('$k_y$')

            if True:
                plt.savefig('A-6-3-tightbindingcontour_noniso.svg', facecolor='white', transparent=False, bbox_inches='tight')

            plt.show()
            ```

        If we are considering a monovalent unit cell, then the Brillouin zone is half filled:

        ![](../images/A6-3-tightbindingmonovalent_noniso.svg)

        ??? example "Filled cell code"

            ``` python
            fig,ax=plt.subplots(1,1)
            x = y = np.arange(-np.pi/a, np.pi/a, 0.1)

            zs = np.array(ep(np.ravel(X), np.ravel(Y)))
            Z = zs.reshape(X.shape)

            maxfilled = np.sort(zs)[int(len(zs)/2)]
            for z in Z:
                z[z>round(maxfilled)] = None

            cp = ax.contourf(X, Y, Z, 11, cmap='binary')
            fig.colorbar(cp) # Add a colorbar to a plot
            ax.set_title('Monovalent tight binding system')
            ax.set_xlabel('$k_x$')
            ax.set_ylabel('$k_y$')

            if True:
                plt.savefig('A-6-3-tightbindingmonovalent_noniso.svg', facecolor='white', transparent=False, bbox_inches='tight')

            plt.show()
            ```