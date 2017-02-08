# RigidBodyDynamics
RigidBodyDynamics implements various rigid body dynamics and kinematics algorithms.

## Design features
Some of the key design features of this package are:
* pure Julia implementation, enabling seamless support for e.g. automatic differentiation using e.g. [ForwardDiff.jl](https://github.com/JuliaDiff/ForwardDiff.jl) and symbolic dynamics using [SymPy.jl](https://github.com/JuliaPy/SymPy.jl).
* easy creation and modification of general rigid body mechanisms (including basic [URDF](http://wiki.ros.org/urdf) parsing).
* extensive checks that verify that coordinate systems match before computation, with the goal of making reference frame mistakes impossible
* flexible caching of intermediate results to prevent doing double work
* fairly small codebase and few dependencies
* singularity-free rotation parameterizations

## Functionality
Current functionality of RigidBodyDynamics includes:
* kinematics/transforming points and free vectors from one coordinate system to another
* transforming wrenches, momenta (spatial force vectors) and twists and their derivatives (spatial motion vectors) from one coordinate system to another
* relative twists/spatial accelerations between bodies
* kinetic/potential energy
* center of mass
* geometric/basic/spatial Jacobians
* momentum
* momentum matrix
* momentum rate bias (= momentum matrix time derivative multiplied by joint velocity vector)
* mass matrix (composite rigid body algorithm)
* inverse dynamics (recursive Newton-Euler)
* dynamics
* simulation, either using an off-the-shelf ODE integrator or using an included custom Munthe-Kaas integrator that properly handles second-order ODEs defined on a manifold.

There is currently partial support for closed-loop systems (parallel mechanisms); more features will be added soon in this area.
Contact is not yet supported.

## Installation

### Installing Julia
Download links and more detailed instructions are available on the [Julia](http://julialang.org/) website.

### Installing RigidBodyDynamics
To install the latest tagged release of RigidBodyDynamics, simply run

```julia
Pkg.add("RigidBodyDynamics") 
```

To check out the master branch and work on the bleeding edge, additionally run

```julia
Pkg.checkout("RigidBodyDynamics")
```

RigidBodyDynamics currently only supports version 0.5 of Julia.

## References
Most of the nomenclature used and algorithms implemented by this package stem
from the following resources:

* Murray, Richard M., et al. A mathematical introduction to robotic manipulation. CRC press, 1994.
* Featherstone, Roy. Rigid body dynamics algorithms. Springer, 2008.
* Duindam, Vincent. Port-based modeling and control for efficient bipedal walking robots. Diss. University of Twente, 2006.

## Related packages
* [RigidBodyTreeInspector.jl](https://github.com/rdeits/RigidBodyTreeInspector.jl) - 3D visualization of RigidBodyDynamics.jl `Mechanism`s using [Director](https://github.com/RobotLocomotion/director).

## Contents
```@contents
Depth = 2
```

## Citing this library
```bibtex
@misc{rigidbodydynamicsjl,
 author = "Twan Koolen and contributors",
 title = "RigidBodyDynamics.jl",
 year = 2016,
 url = "https://github.com/tkoolen/RigidBodyDynamics.jl"
}
```