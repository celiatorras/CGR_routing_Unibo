#### Original Repository

Repository extracted from https://gitlab.com/unibo-dtn/unibo-cgr 

# Unibo-CGR

The core library remains unmodified. The only addition to the original codebase is a script, named example_next_hop.c, located within the \texttt{core} directory.

This script acts as a standalone testbench to validate the Unibo-CGR routing logic:

    Initialization: It sets up the library environment and parses an external text file (contact_plan.txt).

    Simulation: It creates a dummy bundle originating from Node 1 destined for Node 3 to simulate a transmission request.

    Execution: It invokes the core CGR function (UniboCGR_routing) to calculate the optimal path based on the loaded contacts.

    Output: Finally, it retrieves the calculated route and prints the Next Hop to the console for verification.

#### Directory Structure

    Unibo-CGR               _the root directory (README, etc.)_

        core                _core files independent of the BP implementation_
        
            bundles         _implemnetation of internal bundle structures_
            
            cgr             _implementation of the 3 CGR phases_
            
            contact_plan    _implementation of the (internal to Unibo-CGR) contact plan_
            
                contacts
                 
                nodes
                
                ranges
                
            library
                
                log
                    
                list
                    
            library_from_ion 
                    
                rbt
                    
                scalar
                    
            msr              _implementation of Moderate Source Routing_
                
            routes           _implementation of Unibo-CGR routes structures_

            *example_next_hop.c  _Script to test Unibo-CGR functions*

        ion_bpv6            _interface interface code core for ION BP v6_
        
            interface       _interface code core for ION BP v6_

                utility_functions_from_ion

            extensions      _CGRR and RGR code (BP v6)_

            aux_files       _auxiliary files for building in ION BP v6 (ipnfw.c, etc.)_

        ion_bpv7            _the same as above, but for BP v7_

        dtnme

            interface        _interface code for DTNME_

            aux_files        _auxiliary files for building in DTNME (Makefile, Bundle.Router.cc, etc.)_

        docs                 _doxygen html documentation_


#### Copyright

Copyright (c) 2020, University of Bologna. Auxiliary files maintain their original copyright.

#### Funding

This work is partially supported by Spanish MCIN/AEI/ 10.13039/501100011033/FEDER/UE through project PID2023-146378NB-I00
