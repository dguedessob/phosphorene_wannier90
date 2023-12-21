# Projection functions used to construct the initial guess matrix elements. 
# Here, hidrogen-like s and p orbitals have been employed with an additional 
# number of randomly-centred function-type Gaussian functions for the remaining projection functions.
Begin Projections
random 
P :  s,p
End Projections

# Number of iterations for the minimization process.
num_iter = 1000

# Parameter to set the distance in which two points belong to the same shell.
kmesh_tol = 0.0001

# Parameters to make consistent choices of branch cut to avoid local minima trapping.
guiding_centres = true

# Write the diagonal elements of the Hamiltonian in the Wannier basis in eV
write_hr = T

#  Control the interpolation of the k-space Hamiltonian. Here, we avoid to apply the translation condition 
#  to each WF by a basis vector of the super-lattice that minimises the distance between their centres.
use_ws_distance=.false.

# Write the raw data for the interpolated band structure.
bands_plot = T

# Since the systems are not magnetic, it does not consider spinor states.
spinors = false

# Definition of the path in k-space for the bandstructure.
begin kpoint_path ! along the following path
A 0.5 0.5 0.0  Y 0.0 0.5 0.0
Y 0.0 0.5 0.0  G 0.0 0.0 0.0
G 0.0 0.0 0.0  X 0.5 0.0 0.0
X 0.5 0.0 0.0  A 0.5 0.5 0.0
A 0.5 0.5 0.0  G 0.0 0.0 0.0
end kpoint_path
