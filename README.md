# sfal-vsd Program
<details>
<summary>Day 0: System Tools Setup</summary>
    <ul>
        <li>
            <details>
                <summary>Yosys</summary>
                <p>Instructions:</p>
                <pre>
$ git clone https://github.com/YosysHQ/yosys.git 
$ cd yosys 
$ sudo apt install make (If make is not installed please install it) 
$ sudo apt-get install build-essential clang bison flex \
  libreadline-dev gawk tcl-dev libffi-dev git \
  graphviz xdot pkg-config python3 libboost-system-dev \
  libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make 
$ sudo make install

![Screenshot 2024-06-16 214234](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/bebed490-c98a-4b59-8b15-d0576709c9aa)
              </pre>
            </details>
        </li>
        <li>
            <details>
                <summary>Iverilog</summary>
                <p>Instructions:</p>
                <pre>
$ sudo apt-get install iverilog

![Screenshot 2024-06-16 214516](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/77816c6e-1c8d-43ec-9db4-6bc3bbaf10f5)
                </pre>
            </details>
        </li>
        <li>
            <details>
                <summary>GTKWave</summary>
                <p>Instructions:</p>
                <pre>
$ sudo apt update
$ sudo apt install gtkwave

![Screenshot 2024-06-16 214711](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/334d34a0-26ad-4133-af26-461e608977b7)
                </pre>
            </details>
        </li>
    </ul>
</details>
<!--End of Day 0-->
</details>




<details>
    <summary>Day 1: Introduction to Verilog RTL design and Synthesis</summary>
    <ul>
        <li>
            <details>
                <summary>Lab using Iverilog and GTKWave</summary>
                <p>Step 1</p>
                <pre>
Load mux & its testbench to Iverilog.
                </pre>
                <p>Step 2</p>
                <pre>
a.out file is executed.
                </pre>
                <p>Step 3</p>
                <pre>
Load the .vcd file into GTKWave generator.
                </pre>
            </details>
        </li>
        <li>
            <details>
                <summary>Lab using Yosys & Logic Synthesis</summary>
                <ul>
                    <li>
                        <details>
                            <summary>PART 1: Realising the Logic and Generating Library Specific Design</summary>
                            <p>Step 1</p>
                            <pre>
Invoke Yosys by using command yosys
                            </pre>
                            <p>Step 2</p>
                            <pre>
Read the library using read_liberty
                            </pre>
                            <p>Step 3</p>
                            <pre>
Read the design using read_verilog
                            </pre>
                            <p>Step 4</p>
                            <pre>
Define the module that needs to be synthesized
                            </pre>
                            <p>Step 5</p>
                            <pre>
Use command show to view the design
                            </pre>
                            <p>Step 6</p>
                            <pre>
Generate the netlist using abc command
                            </pre>
                            <p>Step 7</p>
                            <pre>
Use command show again to view the library specific design
View the design using library modules
                            </pre>          
                        </details>
                    </li>
                </ul>
                <ul>
                    <li>
                        <details>    
                            <summary>PART 2: Write the netlist & Modify to View Without Additional Attributes</summary>
                            <p>Step 1</p>
                            <pre>
Write the netlist using command 'write_netlist'
                            </pre>
                            <p>Step 2</p>
                            <pre>
View the netlist using command '!gvim'
The Generated Netlist:
                            </pre>
                            <p>Step 3</p>
                            <pre>
Generate a netlist without attributes using -noattr
                            </pre>
                            <p>Step 4</p>
                            <pre>
Use '!gvim' again to view the modified netlist
                            </pre>
                        </details>
                    </li>
                </ul>
            </details>
        </li>
    </ul>
</details>
<!--End of Day 1-->
