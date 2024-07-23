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
                <pre>
Load mux & its testbench to Iverilog.
                    
![1](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/26b24dfa-7a0b-431d-a218-7b8cefa8f989)
    </pre>
                <pre>
a.out file is executed.
![2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/cc657582-2c09-476e-8795-61475698e949)
![3](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/548347d2-f98d-4a39-aab5-79fd6b7f1a9d)
    </pre>
                <pre>
Load the .vcd file into GTKWave generator.
![4](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b0b540c8-e951-4005-8ac5-25abfaeee59e)
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
                            <pre>
Invoke Yosys by using command yosys.
![5](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/9ec94c2c-e818-462e-9f1c-c63acff2cc37)
                            </pre>
                            <pre>
Read the library using read_liberty.
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/45f3b167-0f40-4c32-b038-c53648264079)
                            </pre>
                            <pre>
Read the design using read_verilog.
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/2f111f94-8a85-4e57-8151-a4cbd011fb2b)
        </pre>
                            <pre>
Define the module that needs to be synthesized.
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1308cc8f-ca78-4201-be95-ea30ea7b1dbd)
![9](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/f69641a6-a241-4d53-b20b-162bf4cfb5ec)
                            </pre>
                            <pre>
Use command show to view the design.
![10](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/aa942d01-c1a3-4d01-8372-141b8344f095)
![11](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/95120a2a-9b73-4a32-b97c-ea9d3a0af3c0)
         </pre>
                            <pre>
Generate the netlist using abc command.
![12](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/72059ce1-af52-4b4b-bb35-42e9cf5f4e02)
                            </pre>          
                        </details>
                    </li>
                </ul>
                <ul>
                    <li>
                        <details>    
                            <summary>PART 2: Write the netlist & Modify to View Without Additional Attributes</summary>
                            <pre>
Write the netlist using command 'write_netlist'.
![13](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/bbb8db2f-a56c-4fd5-910b-cfed9a2dd7df)
                            </pre>
                            <pre>
View the netlist using command '!gvim'
The Generated Netlist:
![14](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/9298beda-8bcd-4fdf-ba76-39e4becce7c7)
                            </pre>
                        </details>
                    </li>
                </ul>
            </details>
        </li>
    </ul>
</details>
<!--End of Day 1-->


<details>
    <summary>Day 2: Timing Libs, Hierarchial vs Flat Synthesis & Efficient Flop Coding Styles and Optimization </summary>
    <ul>
        <li>
            <details>
                <summary>Introduction to Timing .libs</summary>
                <ul>
                    <li>
                        <details>
                            <summary>PART 1: Understanding the name of .libs</summary>
                            <pre>
View the library using 'gvim'.
                                
![1](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/63dac140-2d4c-4f71-a6e9-2308460f1d45)
                     </pre>
                            <pre>
Reading the library name contain following information.
From the name, 
'130' technology node '130nm',
 tt_025C_1V80 - referes to PVT cornner
'tt' typical type library,
'025C' referes to temperature, &
'1v80' refers to the voltage.
These give us the operating conditions of the cells in the library
In .lib we have following informtion:
Tells about technology lis CMOS.
Delay module look up table.
Time unit 1ns.
Voltage unit 1v.
Leakage power unit 1nW.
Current unit 1mA.
Pulling resistance unit 1kohm.
Capacitive load unit pf.
Operation condition.
                            </pre>          
                        </details>
                    </li>
                    <li>
                        <details>
                            <summary>PART 2: Understanding the cells in library</summary>
                            <pre>
'cell' refers to the beggining of a new cell
Multiple cells in .lib.
                            </pre>
                            <pre>
Attributes inside cell
![2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/106bac1d-dd60-4855-938e-97f0f4ec239a)
Cell includes information about a cell's:
- Leakage Power of different input combinations
![3](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/4a1c254d-ac9f-47ab-b479-4fe1bcb27721)
- Area
![4](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/3aed5107-a79b-4a15-a34d-ed21d9463fb3)
- Power ports
![5](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/4eba50c5-561a-4c54-beca-0c4dc11d3c3c)
-Input Pins (input capacitance, internal power, transition & delay)
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/10e9fe9d-2b74-4cb1-ab8e-3f8f803ec280)
                            </pre>
                        </details>
                    </li>
                </ul>
            </details>
        </li>
        <li>
            <details>
                <summary>Hierarchial vs Flat Synthesis</summary>
                <ul>
                    <li>
                        <details>
                            <summary>PART 1: Hierarchial Synthesiss</summary>
                            <pre>
Read the library
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1bd8f5e1-53d9-40ad-890c-c04ea5890a98)
                            </pre>
                            <pre>
Read the verilog file
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/193ec11e-3d6f-407f-8c9c-7d28b7c56bcb)
                            </pre>          
                            <pre>
Define the module to be synthesized 
![9](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e283bd31-6d8e-488b-bfef-0e929676d4e4)
View the design hierarchy:
![10](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e3d3d443-78cd-40a1-8795-eddb93bb6087)
                            </pre>
                            <pre>
Generate the netlist
![11](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/188c6142-f1a1-4b46-8e24-8147340fb1a0)
                            </pre>
                            <pre>
run command 'show' to view the design
![12](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/584c9762-a547-456e-8807-fb296047ae3b)
As both submodule 1 and submodule 2 are instantiated seperately, hierachy is maintained and such design is a Hierarchial Design.
                            </pre>
                        </details>
                    </li>
                    <li>
                        <details>
                            <summary>PART 2: Flat Synthesis</summary>
                            <pre>
run command 'flatten' to write a flat netlist
![13](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/370570fa-e13f-448b-95c9-60dddf24c078)
                            </pre>
                            <pre>
Write the netlist to a .v file
![14](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b2949ba1-ffb7-4635-8f31-cde11e99abdc)
                            </pre>
                            <pre>
View the netlist
![15](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/44d020c0-ca7e-4084-801a-8b5e17e43613)
![16](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/9d71a63c-b9ee-4ff7-b090-ffce02414873)
As we can see the sub-modules don't appear in the netlist indicating that the design has been flattened out
                            </pre>
                            <pre>
Run command 'show' to view the flattened module
![17](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/829dc7f4-d79d-4914-afef-431cd97c34f0)
                            </pre>
                        </details>
                    </li>
                    <li>
                        <details>
                            <summary>PART 3: Sub-Module Level Synthesis</summary>
                            <pre>
Read library
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/5950b564-8f13-488d-9410-e01a2163cefe)
                            </pre>
                            <pre>
Read Verilog
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/56eaab51-2a4b-42b4-ba34-4772c210559f)
                            </pre>
                            <pre>
Synthesize at sub module level using 'synth -top'
![18](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/882175df-26b3-49f3-aef9-d30812c96a79)
                            </pre>
                            <pre>
Generate the netlist
![19](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6d72d354-8c12-46d8-87d6-c0ab40b8ef50)
                            </pre>
                            <pre>
Run show command
![20](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/bbdff430-f719-454a-a5d4-234472f2aa60)
Multiple Instances: Such module level synthesis is done when multiple instances of the 
same module are used in the top level design.
Divide & Conquer: If you have a massive design, this type of synthesis can be done to 
generate multiple understandable netlists that can be stitched together.
                            </pre>
                        </details>
                    </li>
                </ul>
            </details>
        </li>
        <li>
            <details>
                <summary>Flop Coding Styles</summary>
                <ul>
                    <li>
                        <details>
                            <summary>PART 1: Different Flip Flops</summary>
                            <pre>
Run iverilog for an Asynchronous Reset D-Flip Flop using its testbench
                            </pre>
                            <pre>
Execute the output file (a.out)
![1asyncreset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a2c136aa-6a18-4447-a15c-ea1056a90411)
![2asyncreset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a55bc066-3531-4151-a724-bfaca18eab41)
             </pre>          
                            <pre>
Run GTKWave to view the behaviour of the Asynchronous Reset D-Flip Flop
Observe the behaviour of the Asynchronous Reset D-Flip Flop
![3asyncreset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/ceae73eb-79d9-4b1e-b5fc-1e9daf40a0de)
                            </pre>
                            <pre>
Repeat Steps 1-3 using the Asynchronous Set D-Flip Flop
![1asynchset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/02900bae-9483-4022-a2c9-a7a0832f5501)
                            </pre>
                            <pre>
Observe the behaviour of the Asynchronous Set D-Flip Flop
![2asynchset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/127550ba-2685-4181-ae41-6ec17754bf40)
                            </pre>
                            <pre>
Repeat Steps 1-3 using the Synchronous Reset D-Flip Flop
![1syncreset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/06c3a9fd-2a66-42e1-be4f-e2cc6dcb89aa)
                            <pre>
Observe the behaviour of the Synchronous Reset D-Flip Flop
![2syncreset](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/78bf143e-3f17-4d7e-827b-699274b6cc30)
                            </pre>
                        </details>
                    </li>
                    <li>
                        <details>
                            <summary>PART 2: Flop Synthesis</summary>
                            <pre>
In Yosys, read the library
Read the verilog file for Asynchronous Reset for D-Flip Flop
Define the module to be sunthesized
![1asynchresetsynth](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b891a620-f7ef-4dce-ab3e-3fbb1d8275ee)
                            </pre>
                            <pre>
Map  the flip flops in the library for synthesis
![2asynchresetsynth](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1e802dc1-63d9-4ff6-b2bd-8a73711ac60d)
                            </pre>
                            <pre>
Generate the netlist
![3asynchresetsynth](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/748eb01e-3c78-4eb0-883d-aebad50cf5e9)
                            </pre>
                            <pre>
Execute show to view the netlist for the Asynchronous Reset D-Flip Flop
![4asynchresetsynth](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/4ba01a9a-412a-4398-8184-2128e863ab34)
                            </pre>
                            <pre>
Execute show to view the netlist design for the Ashynchronous Set D-Flip Flop
![4asynchsetsynth](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6282de6c-3bd4-4e32-b214-bdf13803e8a6)
                            </pre>
                            <pre>
Execute show to view the netlist design for the Synchronous Reset D-Flip Flop
![3syncresetsynth](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b09d0e23-09dc-484e-90e2-f369e79bd801)
                            </pre>
                        </details>
                    </li>
                </ul>   
<details>
                <summary>Special Case Optimizations</summary>
                <ul>
                    <li>
                        <details>
                            <summary>PART 1: mul2 Synthesis</summary>
                            <pre>
In Yosys, read the library
Read the verilog file for mult_2
Define the module to be synthesized
                                
![2mul2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/cd7f31fe-bd3f-4e0b-b7d8-545a5a087fec)
                       </pre>
                            <pre>
Generate the netlist and notice the prompt to not call for abc as there are no cells to be synthesized
![3mul2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1748486f-65a2-4b49-b8de-601cbbbd60d0)
                            </pre>
                            <pre>
Execute show to view the netlist design
![5mul2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/5876951a-d96a-4c75-9467-1d159997ed5a)
                       </pre>
                            <pre>
Write the netlist
View the netlist
![6mul2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1f132b4b-cc56-44bf-aa53-fb7790005aec)
                            </pre>
                        </details>
                    </li>
                    <li>
                        <details>
                            <summary>PART 2: mult8 Synthesis</summary>
                            <pre>
Read the verilog file for mult_8
Define the module to be sunthesized
Generate the netlist and notice the prompt to not call for abc as there are no cells to be synthesized
![1mul8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/cc45b3e5-33a4-4ee1-99c9-499698fd51d9)
![2mul8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/eeedde07-8032-4147-a4bc-dc7fc182b366)
                            </pre>
                            <pre>
Execute show to view the netlist design
![3mul8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/058218b7-9ce3-4f8f-b25e-ecd0cb970f63)
                            </pre>
                            <pre>
Write the netlist
View the netlist
![4mul8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6eac8038-a1a4-4320-8b4b-c01d2b23f69e)
                 </pre>
                        </details>
                    </li>    
                </ul>
            </details>
        </li>
    </ul>
</details>


 <details> 
<summary> DAY 3 - Combinational and Sequential Optimizations </summary>

## DAY 3 - Combinational and Sequential Optimizations

### Intro to optimizations

#### Combinational Logic Optimisation:
#### Why Combinational Logic Optimisation?

-> Squeezing the logic to get the most optimised design (in terms of Area and Power savings- PPA)
#### Technique used for combinatinal optimisation:
1. Constant propogation.
2. Boolean logic optimization.
#### 1. Constant Propagation: 
This is direct optimisation technique using boolean expression.
![1](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/8d967fca-86da-44e4-8d9e-fe2d896ad8e8)
#### 2. Boolean Logic Optimizations: 
This using K-map and Quine Mckluskey and boolean expression methos to optimize the logic.

#### Sequential Logic Optimisation:
#### Basic:
1. Sequestianl constant propogation.
#### Advance:
1. State optimization.
2. Retiming.
3. Sequential logic cloning.
   
#### Sequestianl constant propogation:
Output can be constant irespective of reset and clock.
![2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e45f6400-7d35-4972-aff0-bd521454b0bb)
Note: Every flop if D input tied off is not a sequential constant and Q pin always take a constant value as shown below .
![3](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/3bc6a1c7-cef2-4b09-9d8c-0a695cfa735e)
#### State optimization:
Optimization of unused stae in the finate state meachine.
#### Cloning:
#### Retiming:
Spliting the logic equally to match the timing.
![4](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/910f895d-f349-4980-b3ce-eab759913dcc)

## DAY 3 - Combinational Lab 1
###### Code we are using for optimizing.
module opt_check (input a , input b , output y);
	assign y = a?b:0;
endmodule
###### Invoke the YOSYS tool.
###### Read the library.
###### Read the verilog.
###### Synthsise the code.
![5](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6d9c8ca9-9eb2-46d0-ace7-1f8da232dd3d)
###### To optimze use the command below.
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/935387c5-7855-438b-99da-afa19da59cf2)
###### It has been optimized to AND gate.
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/db8da1e7-7815-495b-acab-0ed1fd910084)
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/cc09cb9b-15cd-4a31-aa75-15298ea474f3)
## DAY 3 - Combinational Lab 2
###### Code we are using for optimizing.
module opt_check2 (input a , input b , output y);
	assign y = a?1:b;
endmodule
###### Invoke the YOSYS tool.
###### Read the library.
###### Read the verilog.
###### Synthsise the code.
![9](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/db61e4a1-1fa6-4d2b-85f1-7eff2b1d77c7)
###### To optimze use the command below.
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c2d54980-8600-425c-8886-7a175d5528ba)
###### It has been optimized to OR gate.
![10](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/f544630a-20e1-4b8f-84f6-1046c66764cb)
## DAY 3 - Combinational Lab 3
###### Code we are using for optimizing.
![11](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/ddc676f7-c5c2-45e3-ac53-51e094d5f6fb)
###### Invoke the YOSYS tool.
###### Read the library.
###### Read the verilog.
###### Synthsise the code.
![12](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/27a6abe2-d574-4309-bb46-c1ea7460be5c)
###### To optimze use the command below.
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c2d54980-8600-425c-8886-7a175d5528ba)
###### It has been optimized to 3 input AND gate.
![13](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c2d02064-9535-4c69-a984-cbde4316f61b)
![14](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/2f8526c6-8df2-4813-b599-dc8d2e7bb288)
## DAY 3 - Combinational Lab 4
###### Code we are using for optimizing.
![16](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/16efc249-6f21-4653-9339-435144eb7116)
###### Invoke the YOSYS tool.
###### Read the library.
###### Read the verilog.
###### Synthsise the code.
![15](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/34461484-1936-4543-96af-82c578fed2a1)
###### To optimze use the command below.
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c2d54980-8600-425c-8886-7a175d5528ba)
###### It has been optimized.
![17](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/3201d217-a34f-4dc1-aab6-0f58da61b79a)
## DAY 3 - Sequential Lab 1
![1](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/64dfac24-5662-4f12-b75e-5867985d98b9)
![2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/0272228c-7dfa-4b4c-a4a2-219c4ba8a0eb)
![3](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/5a948d26-673f-40e1-b7eb-04d85b0bdad8)
![4](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/25c903e3-5fd3-4abc-b04d-bb6741998c5e)
![5](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/76bb9f9a-d93a-4985-8b93-df7edd9adff8)
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/42196f31-bdce-4429-b415-87a5b7a65144)
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b6059a70-096f-412e-ad2e-8aa3f19290ce)
## DAY 3 - Sequential Lab 2
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/329128e2-033d-455e-a9fe-cc55a1b4620d)
![9](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/90366b2f-9235-4d22-8e75-1d194586fb75)
![10](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e55be759-bcf8-49f6-921e-4e051f4ab729)
![11](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e46d556b-7b7d-421d-9d10-312f298c8342)
![12](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/466923d4-382a-470e-b20f-be5778f2302d)
## DAY 3 - Sequential Lab 3
#### Unused Output Optimization:
![16](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/651bb4ce-d31c-42c5-8f76-77dc4935b4e5)
![14](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b71406ad-1257-46bc-92e5-0b105d5e101d)
![15](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/cfbcadc1-5b7f-4e49-9d3c-896c5ad121b9)
![17](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a807c47a-3439-403e-abe2-d29570601509)
#### After mofifying above code:
![18](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c9687002-7418-4778-ad13-096bc8e4eb6a)
![19](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/66c2b61f-1353-4893-9585-d9686bee020b)
![20](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/573712d7-c535-4e18-abc2-b7531261cb72)
 </details> 
 <details> 
<summary> Day 4 - GLS (Gate level simulation), blocking vs non-blocking and Synthesis-Simulation mismatch </summary>
	 
## Day 4 - GLS (Gate level simulation), blocking vs non-blocking and Synthesis-Simulation mismatch

### Gate level simulation (GLS) :
#### What is GLS?
Running test bench wiht Netlist as design under test.
#### Why is GLS?
1. To verify the logical corrects of design after synthesis.
2. Ensuring the timing of the design is met.
![3](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a99cd9aa-0695-45e1-87d8-22ec1ab815f5)
![2](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a650806b-ab69-44e9-a68c-c8fd01016014)

#### Why we need to validate the functinality of the Netlist?
Because there could be synthesis and simulation mismatch.

### Synthesis simulation mismatch :
#### Simulation mismatch happens becuse of following reasons.
1. Missing sensistivity list.
2. Blocking vs Non blocking assignment.
3. Non standard verilog coading.

### Missing sensistivity list :
In verilog code we need to take care of the providing sensistivity list.
![4](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/ee0d3c2f-689e-44d2-95cb-3fed137b0741)
In simulation time it looks like double edge flop.
In synthesis it looks line mux.

### Blocking vs Non blocking assignment :
In side always block we use blocking and non clocking state ments.
#### Blocking (=):
Here the blocking stesments are executed in the sequesntial manner.
Use always non blokcing with sequential circuit.
![6](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b36585af-1335-4936-8fbb-c966e2a08b8c)
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1a59d6a6-1630-4259-89f2-c70bcda0f6d0)
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/68a3f44a-7a70-4e97-83e3-d52bdfab3cdc)

#### Non Blocking (<=):
Here executes all the RHS and assigned to LHS means non blocking statements are executed in the parllel.

## DAY 4 - GLS Lab 1
![9](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c0faffdc-02ff-40bb-8f37-eb0d629d2ff7)
![10](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/37b354ba-38d8-464e-a8ea-40932644b5dc)
![11](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/b3d0c741-97e5-4186-9a7c-cc796f5d9cce)
![12](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/bb5668ce-cef8-4b23-9749-84fdcfd5e879)
#### Do GLS:
![13](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/88e74866-584a-4aaf-80af-96f9477dded3)
![14](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/faaabeca-46b2-4bab-8d99-eeb8aa9055ca)

## DAY 4 - GLS Lab 2
![15](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/7b91c9f4-bd39-4f05-992a-ecf7965c16c4)
![16](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6e030621-5bc6-4465-a610-a803c5607063)

#### Do GLS:
Synsthesis simulation miss match.
![17](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6be7ce45-b8cd-4846-9e67-49d4a2f600c7)
![18](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/f1edef6a-571e-408a-b114-0ba98ad217a4)

## DAY 4 - GLS Lab 3
![19](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/02618158-f70a-418e-b834-00675249e47f)
![20](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a90df7ef-663b-459c-9af9-9a5306460b80)
![21](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/60b28480-8752-4104-bb1c-db5057be09aa)
![22](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/6c45d4e1-2769-49a7-9578-225d73861932)

#### Do GLS:
![23](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/12be3aea-67d4-4c9d-88ac-1c89efc28b4c)
![24](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/4e9143a1-5746-47cc-8c3f-0d9b91889b93)

 </details>

  <details> 
<summary> Day 5 - Advanced synthesis and STA with design compliler </summary>
	 
## Day 5 - Advanced synthesis and STA with design compliler
## Logic Synthesis
### What is synthesis?
RTL to gate level transistion is called synthesis.
Or the converint design into gates and making connection between the gates.
The out put of the synthesis is called as gate levle Netlist.
![7](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/f139d56f-76e1-4427-9fd7-50ed1df5d909)

### What is .lib?
It is a collection of logic modules incluedes logic gates. It contains information of standard cell like timing, area, power.<br>
It contains different flavors of same gates.<br>
Ex:<br>
2 input AND : slow, medium, fast.<br>
3 input AND : slow, medium, fast.<br>
4 input AND : slow, medium, fast.<br>
![8](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/62608918-91c3-4dd7-ae0d-b9d701173cfe)
![9](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/1b357167-76d1-4298-a84d-1cbd27df5547)
![10](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e3a4cf92-3fd4-42b1-9fe2-080ad91f55a9)

In .lib it contain fast and slow working cells. We requires fast workign cells to meet setup and slow working cells to meethe hold requirement.

![11](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e906f7f5-7d0c-4b85-82d2-f8ec5fe94386)
![12](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/5674e541-e9bc-41ce-8bdf-c2037c71f115)
![13](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/be3ac607-07c4-472e-b7c0-4314e47126c9)
![14](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/688f7133-505e-4b1b-b1be-30654bb718a7)
![15](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/d64514f2-2f69-4eb8-8359-d1f2bcdf94ff)
![16](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/81829887-f307-4de5-8c0b-65d4a1cffb1c)
![17](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c17e9851-7f9f-4f33-8c9b-c085a810e136)
![18](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/47241688-ce69-4954-9d45-995061388649)

## Advace Synthesis and STA Using DC
## Introduction Design Compiler
![19](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/db6bc802-6f6d-4357-8d97-32d49429bc3e)
![20](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/be33e049-29eb-4dea-8c89-210329dd227e)
### Terminology used in DC compiler
.LIB library which contains standard cells <br>
.DB same as LIB but different format DC uses .db format for cell libraries <br>
.DDC format to store design information  .DC can read and write out in .DDC <br>
.DESIGN  RTL models <br>

### SDC Format
Constraints for power, area and timing <br>
SDC syntax is based on TCL
![22](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/e1244fd6-e1d5-4852-9807-1e6e5a607497)
![23](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/9478d986-466c-4dc6-a5cb-b098d2e5b90b)
![24](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/56aba3cd-ab59-4d3d-988f-c2a4f3e5da72)

## DAY 5 - Ivoking DC basic set up Lab 1
![25](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/d061c9a7-5490-4cbb-9595-5fdaf5b70c29)
![26](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/2c8d2cc9-e594-40ee-b9de-7e95431f2c95)
![27](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/c1250370-4a61-439b-92a4-4335e2502cf9)
![28](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/93f84c54-e916-45c6-af71-39b62d1cefa6)

Library is not liked so if write into .v file to understand the design it uses the virtual library. <br> There is no standard cell information is provided so it will written out using Gtech cells. <br>

![28](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/ce4a5b96-c0f1-4e89-aae2-936a9fb71f85)
![29](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/95ea773c-96bd-4580-aa6d-4f8f5674da86)

### Read the library in .db format
After reading the library again if write the verilog its writting in gtech cells formtat.<br>
![31](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/3a55124c-3f91-4bf1-b462-4af27d6f495f)
To resolve this we need to set the target_library and link_library. <br>
![32](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/da5a197a-8ab4-4aba-b196-7aeaf1282644)
### Link the library
![33](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/2bc9c980-8a2a-4b1b-817a-743ec511ff11)
### Compile the design and then write the design 
![34](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/a9c0247a-c03c-4b39-bf85-b9ad0e628b52)
![35](https://github.com/bhaskarhadimanig/sfal-vsd/assets/157913378/2727e7d6-2167-476f-996d-eccd77dbffe5)
Write ddc command to write ddc "write -f ddc -out <filename.ddc>".
## DAY 5 - Ivoking Design Vision Lab 2
To invoke design vision tool need to use design_vision command.<br>
Design vision is the GUI format of DC.<br>
There we can able to read the ddc and .v file.<br>
![36](https://github.com/user-attachments/assets/4c57079a-77f9-4a27-ac41-3b85fa2defa6)
![37](https://github.com/user-attachments/assets/0524377c-1df4-44b7-a7e3-e84b6ddfba58)
The file format ddc is propritory format of synopsis so if you are using ICC for pysical design if we read ddc is enough.<br>
It will read all the information like libraries and constraints no need to read explcitly.
## DAY 5 - Set up DC using set up file Lab 3
Insted of reading or setting of libraries explicitly we can configure in the setup file.<br>
In working directory we need to create ".synopsys_dc.setup" file and add all the set up in that file.<br>
![38](https://github.com/user-attachments/assets/7a524315-e015-466f-8696-76860d897504)
After creating setup file and if we invoke dc_shell no need to set some of the information required for DC like target_library and link_library explicitly.<br>
![39](https://github.com/user-attachments/assets/431f435b-f097-4862-a162-5f795ee90a05)

## TCL Scripting
### TCL Scripting to set variable and print the value of variable
set i 0 -> To setting a variable i to a value 0 
echo $i -> To print the value of i in console
incr i 	-> To increment the value of i
![40](https://github.com/user-attachments/assets/0715fee6-3837-4185-8713-4ce8cf07d288)

### TCL Scripting defing for loop
![41](https://github.com/user-attachments/assets/ba1c7ce3-7c11-4143-8cd6-0c585aedf08d)

### TCL Scripting defing while loop
![42](https://github.com/user-attachments/assets/646a08a1-ed0d-4f1a-96f8-7c19c7af00f6)
![43](https://github.com/user-attachments/assets/4fe60c23-e46b-43fe-bd0e-f00a31339ab9)

### TCL Scripting creating list
![44](https://github.com/user-attachments/assets/49a8c372-77de-457b-9b65-a7a245c5ae6b)

### TCL Scripting foreach to iterate through list
![45](https://github.com/user-attachments/assets/07898819-702c-4033-a588-22e894e93e6d)

### TCL Scripting foreach_in_collection of DC
![46](https://github.com/user-attachments/assets/81c9c11d-6a4c-4464-8eb8-f7176da21345)

### TCL Scripting creating .tcl script and sourcing
Create the tcl script ans save the script with .tcl extention and save the file.
The tcl script can be source in shell.
![48](https://github.com/user-attachments/assets/8a482eab-4533-48d0-ac17-03b1170a2783)
![47](https://github.com/user-attachments/assets/6f2643e8-9f16-4636-adac-6c76b6c67030)
![49](https://github.com/user-attachments/assets/c2236418-9cb0-4bb2-bab5-fb9be4366281)

</details>
<!--End of Day 5 -->

<!--Start of Day 6-->
<details> 
<summary> Day 6 - Basics of STA </summary>
<ul>
<li>
<details> 
<summary> Introduction to STA </summary>
		 
## Day 6 - Introduction to STA
### Min and Max Delay:
![1](https://github.com/user-attachments/assets/168b6bbe-3b16-459e-bdac-bd616de6576a)
### Delay:
So delay is a function of input transition and load capacitance.<br>
Delay of any gate is function of input transition and out put load.<br>
Where load is not only because of leangthy nets and also depends on number of load connected to it.<br>
![2](https://github.com/user-attachments/assets/27c22a1c-4dff-41de-8d57-b17dce0cfcd4)
![3](https://github.com/user-attachments/assets/35ad8416-9796-4561-8cfd-4b161d42042e)
![4](https://github.com/user-attachments/assets/56ee13ba-2eed-4ebe-9c7b-72b5dccc6bd8)
### Time Arcs:
![5](https://github.com/user-attachments/assets/5efc3db7-68e1-4e18-ba9e-f8c730935625)
![6](https://github.com/user-attachments/assets/41b1ed3f-325f-4dfb-bc24-01e013d62b2e)
![7](https://github.com/user-attachments/assets/ce73f531-7723-4fca-9b51-165d0a77ad00)

</details>
</li>
<li>
<details> 
<summary> Constraints </summary>
	
## Day 6 - Constraints
![8](https://github.com/user-attachments/assets/696fb917-cbb1-422f-b96f-f95f7f2369b1)
![9](https://github.com/user-attachments/assets/1db1c382-4aa6-4aec-a1c8-bd45bef7d5d5)
![10](https://github.com/user-attachments/assets/644d994b-6e37-41b5-a635-b6cc9c0978ff)
Practically if curcuit has to work at some frequency then that decides the allowable cobinational delay.<br> 
Coinatinal delay not decides the frequency fequency of circuit has to work decides the allowable combinational delay means clock period is limiting the combinational logic.<br>
Example if circuit has to work at 500MHz or clock period is 2ns. And if TCQ delay of flip flop is 0.5ns. Then combinational delay should be of 1ns.<br>
The constraint given to the synthesis tool is operating frequency or clock period as constraint. The tool will pick appropriate cells for the combinational logic to meet the timing.<br>
![11](https://github.com/user-attachments/assets/f4046acc-4bd4-4163-9b7b-71016cea4261)
Based on the IN to REG, REG to REG and REG to OUT we need to constrain the design.<br>
REG to REG : All the are constrained by clock. Once clock is defined then tool will constrin the combinational ciruit delay.<br>
REG to OUT : Constrained by Output external delay (we need to constraint the logic) and clock period.<br>
IN to REG  : Constrained by Input external delay (we need to constraint the logic) and clock period.<br>
![12](https://github.com/user-attachments/assets/0b2eb2d2-7dda-4fa1-af62-3db83bbd52b5)
![13](https://github.com/user-attachments/assets/ef57efaa-acee-48ea-afbc-d26276342667)
![14](https://github.com/user-attachments/assets/d1e8c537-2464-4d78-a591-a9056e85d0a7)
Based on the Output external delay and Input external delay tool will calculate the required combinational delay in REG to OUT and IN to REG path and is called IO modeling.<br>
This can be constrained based on:<br>
1. standart interface specification.<br>
2. Io budgeting based on interation with other modules.<br>
![15](https://github.com/user-attachments/assets/1ef3d781-9b1c-44cb-b8a7-f6df19f8b938)

</details>
</li>

<li>
<details> 
<summary> Input Transition and Output Load </summary>

## Day 6 - Input Tran and Output Load
![16](https://github.com/user-attachments/assets/6665f51b-c665-4ca9-aaba-48edb6dd2bb4)
![17](https://github.com/user-attachments/assets/d2e6f6ba-b9dd-41b4-90bd-acebc0cc8a83)
![18](https://github.com/user-attachments/assets/db96eaf6-f237-4d1a-a9ac-9afb5438b56c)
![19](https://github.com/user-attachments/assets/a491bb7b-1723-4baf-a826-5b9aa9286a92)
Generallyt IO delay modeling is done on 70% - 30% thub rule, menas 70% for external delay and 30% for internal delay.
![20](https://github.com/user-attachments/assets/93a9faa4-814f-4807-9f0a-f03e1e09851c)
</details>
</li>

<li>
<details> 
<summary> Lab </summary>

## Day 6 - Lab 1 - Timing .lib
### In .lib we have following information:
tt_025C_1V80 - referes to PVT cornner
'tt' typical type library,
'025C' referes to temperature, &
'1v80' refers to the voltage.<br>
These give us the operating conditions of the cells in the library.<br>
In .lib we have following informtion:<br>
Tells about technology lis CMOS.<br>
Delay module look up table.<br>
Time unit 1ns.<br>
Voltage unit 1v.<br>
Leakage power unit 1nW.<br>
Current unit 1mA.<br>
Pulling resistance unit 1kohm.<br>
Capacitive load unit pf.<br>
Operation condition.<br>
### default_max_transition : 1.5000000000;
Load capacitance is depends on output capacistance, net capacitance and input capacitance of other gate.<br>
This may incress the load capacitance this may leads to incress the transition.<br>
So in library means in .lib default transition is set based on this DC can do buffering.<br>
![21](https://github.com/user-attachments/assets/89d4c0f7-49d3-447a-ae3c-a05e13a26fc9)
### Delay Model Look Up Table:
It contains the delay information base on the Input transition and Output load.<br>
Based on tranition and load DC will calculate the delay of the gate.<br>
![22](https://github.com/user-attachments/assets/47071271-5483-44e9-9de9-6cc85033a3c1)
### Unetness:
OR and AND gate have positive unetbess.<br>
NOT, NAND and NOR gave negative unetness.<br>
XOR have both positive and negative unetness.<br>
Tool will propogate the transition though the circuit based on the unetness.<br>
![24](https://github.com/user-attachments/assets/856d4415-2a22-436f-85b8-59fa0157024e)
## Day 6 - Lab 2 - Timing .lib
CLK_N is the active low clock. Attribute clock is true. While for the D pin, attribute clock is false so based on the this attribute tool knows is it a clock pin or not.<br>
timing_sense : "non_unate" - non_unate means with respect to clock Q has no unateness.<br>
timing_type : "falling_edge" - sequential timing arc.<br>
For positive edge flip flop setup time is mesure with respect to raising edge (setup_rising) and for negativ edge flip flop setup time is mesure with respect to falling edge (setup_falling).<br>
![25](https://github.com/user-attachments/assets/1d4fc5b3-9e8e-40fd-bdc9-18b3e9f43209)
![26](https://github.com/user-attachments/assets/83053eb3-7916-4468-96e3-f3171b07fae7)
For latch its visversa.<br>
![27](https://github.com/user-attachments/assets/f6618272-a169-40b9-933c-bef478562e01)
## Day 6 - Lab 3 - Exploring .lib
### How to query the properties of .lib from DC sheel:
dc_shell> list_lib : it tells what the is library loaded in the DC shell.<br>
get_lib_cells */*and* : to get the perticular type of cell.
![28](https://github.com/user-attachments/assets/bcf21067-d571-431c-a5a5-fc740cf6bcbb)
Command to get the list of that particular cell as a list:
![29](https://github.com/user-attachments/assets/4dd7e67e-452a-4cce-bf82-1a41b35741b4)
Command to get the pins in a cell (sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand4bb_2):
dc_shell> get_lib_pins sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand4bb_2/*
![30](https://github.com/user-attachments/assets/ec47fa95-6659-4a2d-aa3e-e26a43370c4d)
#### To fetch pin direction of each pin:
sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0
![31](https://github.com/user-attachments/assets/0135610c-4b5a-458a-b4bc-c64c7236d5a0)
#### To get pin direction:
![32](https://github.com/user-attachments/assets/efa59b16-7b0c-4ad4-a8dd-9349fbf6ef0b)
#### To get the functinality of out pin:
![33](https://github.com/user-attachments/assets/a3de99df-d86d-481b-9ec4-d80adc79e060)
#### Script to get function for list of gates:
![34](https://github.com/user-attachments/assets/aedcba8c-9ae3-4283-8bc7-b37155ca28e5)
![35](https://github.com/user-attachments/assets/f4993e0c-f7eb-4b61-9c36-ec3f5118b3fd)
#### To get area of perticular gate:
![36](https://github.com/user-attachments/assets/8ff7a4f4-54a6-45d1-895c-611604d098dc)
#### To get capacitance of perticular gate:
![37](https://github.com/user-attachments/assets/2870ece8-c10c-49fe-b118-95f00e2c7780)
#### To check clock pin or not of perticular gate:
get_lib_attribute sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__and2_0/A clock
#### To get all the sequential cells in the library:
get_lib_cells */* -filter "is_sequential == true"
#### Command to list all atributes:
list_attributes -app
</details>
</li>
</ul>
</details>

<details> 
<summary> Day 11 - Introduction to BabySoC </summary>

## Day 11 - Introduction to BabySoC
### What is SoC
SoC is a single-die chip that has some different IP cores on it. These IPs could vary from 
microprocessors (completely digital) to 5G broadband modems (completely analog).<br>
The design of a system on chip usually includes a central processing unit, memory, ports for input 
and outputs, secondary storage devices, and peripheral interfaces such as Timers, etc.<br> 
Depending upon the requirement it can also consist of a digital or analog signal processing system 
or a floating-point unit.<br>
SoC with equivalent functionality will have increased performance and reduced power
consumption as well as a smaller semiconductor die area.<br>
### My mobile processor name is snapdragon 
![810_3](https://github.com/user-attachments/assets/3c87bfd9-4dec-48af-8f4f-4bd7d1567c41)

### Types of SOC
![1](https://github.com/user-attachments/assets/2de7c5c5-610d-4010-8c67-6689dba510d9)
![2](https://github.com/user-attachments/assets/e4a12a93-e1e8-42bf-8646-d69a5b7307db)

### SOC Design Flow
![3](https://github.com/user-attachments/assets/38bd8a8c-3310-4108-877a-72ee8fbb2e07)

## Introduction to BabySoC
![4](https://github.com/user-attachments/assets/5e7724ed-87bb-4968-b27b-58ec0e9d0744)

### Components of BabySOC
RVMYTH: RVMYTH core is a simple RISCV-based CPU.<br>
PLL: A phase-locked loop or PLL is a control system that generates an 
output signal whose phase is related to the phase of an input signal. 
PLLs are widely used for synchronization purposes, including clock 
generation and distribution.<br>
DAC: A digital-to-analog converter or DAC is a system that converts a 
digital signal into an analog signal. DACs are widely used in modern 
communication systems enabling the generation of digitally-defined 
transmission signals.<br>

</details>


<details> 
<summary> Day 12 - BabySoC Modelling </summary>
	
## Day 12 - BabySoC Modelling
![5](https://github.com/user-attachments/assets/8e09d6c6-9a51-4602-a3f5-02670a4f6f8c)

### Components of BabySOC
#### RVMYTH:
RVMYTH core is a simple RISCV-based CPU, introduced in a workshop by RedwoodEDA and VSD. During a 5-day workshop students (including middle-schoolers) managed to create a processor from scratch. The workshop used the TLV for faster development. All of the present and future contributions to the IP will be done by students and under open-source licenses.<br>

#### PLL:
A phase-locked loop or PLL is a control system that generates an output signal whose phase is related to the phase of an input signal. PLLs are widely used for synchronization purposes, including clock generation and distribution.<br>

#### DAC:
A digital-to-analog converter or DAC is a system that converts a digital signal into an analog signal. DACs are widely used in modern communication systems enabling the generation of digitally-defined transmission signals. As a result, high-speed DACs are used for mobile communications and ultra-high-speed DACs are employed in optical communications systems.<br>
![4](https://github.com/user-attachments/assets/26e01fa8-e47e-4cf4-a6f4-ba943df7a68b)

#### VSDBabySoC Modeling
Here we are going to model and simulate the VSDBabySoC using iverilog, then we will show the results using gtkwave tool. Some initial input signals will be fed into vsdbabysoc module that make the pll start generating the proper CLK for the circuit. The clock signal will make the rvmyth to execute instructions in its imem. As a result the register r17 will be filled with some values cycle by cycle. These values are used by dac core to provide the final output signal named OUT. So we have 3 main elements (IP cores) and a wrapper as an SoC and of-course there would be also a testbench module out there.<br>

#### RVMYTH:
RVMYTH - Risc-V based MYTH (Microprocessor for You in Thirty Hours)<br>
RISC stands for Reduced instruction set computer.<br>
It is an Instruction Set Architecture (ISA).<br>
#### A simple one cycle CPU for Risc-V
![6](https://github.com/user-attachments/assets/2eb8512c-d392-4825-b014-c2b2fd85aa2e)
![7](https://github.com/user-attachments/assets/f3cb831b-411e-4dfa-b0b9-dc4751dcc703)
#### PLL:
PLL stands for Phase-Locked Loop, and it's a fundamental component in electronics used for various purposes including to generate, stabilize, modulate, demodulate and more.<br>
Clock Signal is generated using Quartz crystal oscillators.
#### Componets of PLL:
#### 1. Phase detector.<br>
The phase detector compares the phase difference between two signals: the reference input signal and the feedback signal from the VCO output.<br>
It generates an error signal that is proportional to the phase difference between these two signals.<br>
Common types of phase detectors include the XOR gate (for digital PLLs) or a mixer (for analog PLLs).<br>
#### 2. Loop filter.<br>
This is a network of capacitors and resistors used in the feedback path of the PLL.<br>
It integrates the control voltage from the LPF to provide the required dynamic response and stability of the PLL loop.<br>
The loop filter determines the bandwidth and damping characteristics of the PLL, affecting its transient response and noise performance.<br>
#### 3. Voltage controlled oscillator.<br>
The VCO generates an output signal whose frequency is directly proportional to the input control voltage.<br>
In a PLL, the control voltage comes from the LPF, which adjusts the VCO frequency to minimize the phase difference between the reference input and the feedback signal.<br>
VCOs can be implemented using various technologies such as LC circuits, ring oscillators, or digital controlled oscillators (DCOs) depending on the application.<br>
#### 4. Frequency divider.<br>
A frequency divider is used to divide down the output frequency of the VCO.<br>
This allows for generating output frequencies that are multiples or fractions of the VCO frequency, which can be useful for frequency synthesis applications.<br>
The divided signal may also be used as a feedback signal to the phase detector instead of the VCO output directly.<br>

#### DAC (Digital to Analog Conveter):
A Digital to Analog Converter (DAC) converts a digital input signal into an analog out signal.<br>
#### There are two types of DACs :
1. Weighted Resistor DAC<br>
2. R-2R Ladder DAC<br>
#### 1. Weighted Resistor DAC :
A weighted resistor DAC produces an analog output, which is almost equal to the
digital (binary) input by using binary weighted resistors in the inverting adder
circuit. In short, a binary weighted resistor DAC is called as weighted resistor
DAC.<br>
![8](https://github.com/user-attachments/assets/1b76989e-b839-4315-9c5c-fddd0b5db615)

#### 2. R-2R Ladder DAC :
The R-2R Ladder DAC overcomes the disadvantages of a binary weighted 
resistor DAC. As the name suggests, R-2R Ladder DAC produces an analog 
output, which is almost equal to the digital (binary) input by using a R-2R ladder 
network in the inverting adder circuit.<br>
![9](https://github.com/user-attachments/assets/17a22c3f-a635-440e-9956-b4a73a46b30f)

RVMYTH is a digital block, so yes we can use a HDL for designing and check its functionality using a testbench. <br>
DAC and PLL are analog so verilog can not synthesise analog block's.<br>
But we are going to simulate it using verilog here we will be using data-types such real its a non synthesizable.We are going to simulate “functionality” to verify its logical correctness.<br>
So we will be using verilog to model - and use iverilog to compile and simulate Use GTKWave to see the waveforms & debug.<br>

#### Few tips on modelling your design
1. Avoid race Conditions 
2. Use a optimized Testbench for debugging your design
3. Creating models that simulate faster…
4. Case statement behaviour.
![10](https://github.com/user-attachments/assets/0c810805-c049-4100-99e3-23b35d59e9a4)

#### Follow these steps to model the IP cores separately
#### For modelling RVMYTH(RISC-V)
1. git clone https://github.com/kunalg123/rvmyth/<br> 
2. cd rvmyth<br> 
3. csh<br>
4. iverilog mythcore_test.v tb_mythcore_test.v<br> 
5. ./a.out<br>
6. gtkwave <file_name>.vcd &<br>
7. Add the required waveforms.<br>
![11](https://github.com/user-attachments/assets/e23bf46e-f70b-414d-93f6-d8af5d0c56c7)

#### For modelling DAC
1. git clone https://github.com/kunalg123/rvmyth/ /// ignore if already done once!<br>
2. cd rvmyth <br>
3. csh<br>
4. iverilog avsddac.v avsddac_tb_test.v<br>
5. ./a.out<br>
6. gtkwave <file_name>.vcd &<br>
7. Add the required waveforms.<br>

## Steps to be followed for pre-synthesis modeling of BabySoC
#### Details on VSDBabySoC please find the repo <a href="https://github.com/manili/VSDBabySoC?tab=readme-ov-file#step-by-step-modeling-walkthrough">Click Here</a>.
#### 1. Install These Required Packages:<br>
 $ sudo apt install make python python3 python3-pip git iverilog gtkwave docker.io<br>
 $ sudo chmod 666 /var/run/docker.sock<br>
 $ cd ~<br>
 $ pip3 install pyyaml click sandpiper-saas<br>
#### 2. Clone the repository of VSDBabySoC project contain design and testbench files:<br>
 git clone https://github.com/manili/VSDBabySoC.git<br>
#### 3. Change directory to VSDBabySoC project directory:<br>
 cd VSDBabySoC<br>
#### 4. To generate .v file from .tlv file using sandpiper-saas using belos command:<br>
 sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/<br>
 It will generate following .v files rvmyth.v and rvmyth_gen.v.
#### 5. To compile and simulate VSDBabySoC use the following command:<br>
 iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module<br>
 This will generates the pre_synth_sim.out file in output folder.<br>
#### 6. Change directory to output:<br>
 cd output<br>
#### 7. To generate pre_synth_sim.vcd file run the command:<br>
 ./pre_synth_sim.out<br>
 This will generate the pre_synth_sim.vcd file.<br>
#### 8. Simulate using gtkwave by running command:<br>
 gtkwave pre_synth_sim.vcd<br>

#### 9. Simulate output:<br>
 ![13](https://github.com/user-attachments/assets/25c6bb58-9028-4f7c-b858-d149b5b8fb5d)

</details>


<details> 
<summary> Day 13 - Post-Synthesis Simulation (GLS) of BabySoC </summary>
	
## Post-Synthesis Simulation (GLS) of BabySoC
### Why do pre-synthesis? Why not just do post-synthesis?
Pre-synthesis simulation is done according to the logic you have designed for and 
written -> only functionality.<br>
Post synthesis simulation / ‘gate level simulation’ is done after synthesis
considering each and every gate delays into account. reports the violations in both 
functionality and timing.<br> 
This also show’s the mismatches we are likely to get due to wrong usage of 
operators and inference of latches.<br>
For ex: using ‘X’(simulator terms/ synthesizer terms) - ‘Unknown’/“Don’t care”.<br>

### GLS: a brief introduction
The term "gate level" refers to the netlist view of a circuit, usually produced by logic synthesis.<br>
So while RTL simulation is pre-synthesis, GLS is post-synthesis.<br>
The netlist view is a complete connection list consisting of gates and IP models with full functional and timing behavior.<br>
RTL simulation is a zero delay environment and events generally occur on the active clock edge.<br>
GLS can be zero delay also, but is more often used in unit delay or full timing mode.<br>
Gate level simulation is used to boost the confidence regarding implementation of a design and can help verify dynamic circuit behaviour, which cannot be verified accurately by static methods. It is a significant step in the verification process.<br>

### Converting .lib file to .db file
Convert .lib file to .db file using Synopsys Library Compiler (lc_shell). We need .db format for avsddac.lib, avsdpll.lib & sky130_fd_sc_hd__tt_025C_1v80.lib.<br>

### Converting avsddac.lib to avsddac.db
cd /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib<br>
lc_shell<br>
read_lib avsddac.lib<br>
write_lib avsddac -format db -output avsddac.db<br>
![1](https://github.com/user-attachments/assets/c8a3ce17-a734-4bd1-af09-57f2bdb36da0)

### Converting avsdpll.lib to avsdpll.db
cd /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib<br>
lc_shell<br>
read_lib avsdpll.lib<br>
write_lib avsdpll -format db -output avsdpll.db<br>
But while reading avsdpll.lib we are getting some error as shown below screen shot.<br>
![2](https://github.com/user-attachments/assets/e28a9906-ebe6-4b15-99d3-2fb43ee0e529)
After editing avsdpll.lib lib file can able to read the file and convert to avsdpll.db file show in screen shot.
![3](https://github.com/user-attachments/assets/759707f9-bfe8-4a80-8852-71c701c5c6eb)

### Converting sky130_fd_sc_hd__tt_025C_1v80.lib to sky130_fd_sc_hd__tt_025C_1v80.db
Download the latest sky130_fd_sc_hd__tt_025C_1v80.lib from the path - https://github.com/efabless/skywater-pdk-libs-sky130_fd_sc_hd/tree/master/timing Synatx to download the raw file in Linux<br>
#### Use below command to downlaod latest sky130_fd_sc_hd__tt_025C_1v80.lib file:
wget https://raw.githubusercontent.com/efabless/skywater-pdk-libs-sky130_fd_sc_hd/master/timing/sky130_fd_sc_hd__tt_025C_1v80.lib<br>

After downloading latest sky130_fd_sc_hd__tt_025C_1v80.lib file convert the sky130_fd_sc_hd__tt_025C_1v80.lib to sky130_fd_sc_hd__tt_025C_1v80.db<br>
cd /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib
lc_shell
read_lib sky130_fd_sc_hd__tt_025C_1v80.lib
write_lib sky130_fd_sc_hd__tt_025C_1v80 -format db -output sky130_fd_sc_hd__tt_025C_1v80.db
![4](https://github.com/user-attachments/assets/045383ad-0cf7-4629-96b0-b1137f9670fd)

## Lab - Synthesis and Post Synthesis (Gate Level) Simulation
### Below commands to perform the synthesis:
cd /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC<br>
dc_shell<br>
set target_library /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.db<br>
set link_library {* /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsdpll.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsddac.db}<br>
set search_path {/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/include /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/module}<br> 
read_file {sandpiper_gen.vh  sandpiper.vh  sp_default.vh  sp_verilog.vh clk_gate.v rvmyth.v rvmyth_gen.v vsdbabysoc.v} -autoread -top vsdbabysoc<br> 
link<br> 
compile_ultra<br>
write_file -format verilog -hierarchy -output /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/output/vsdbabysoc_net.v<br>
report_qor > report_qor.txt<br>
![5](https://github.com/user-attachments/assets/ad698170-5a2f-47ec-885c-57289ff991a4)
![6](https://github.com/user-attachments/assets/ea9674cb-7aff-416c-a271-4b5295bcf7b9)
![7](https://github.com/user-attachments/assets/8f387a4d-6b73-440f-bcd6-8e3690258688)
### QOR Report:
![8](https://github.com/user-attachments/assets/62924f0e-fc80-44ff-b387-e8ddbf65be99)
![9](https://github.com/user-attachments/assets/59007962-bf08-4d22-94a4-4e82277318a0)

</details>
