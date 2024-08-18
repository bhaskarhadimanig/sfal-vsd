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
```sh
cd /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC
dc_shell
set target_library /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.db
set link_library {* /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsdpll.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsddac.db}
set search_path {/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/include /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/module} 
read_file {sandpiper_gen.vh  sandpiper.vh  sp_default.vh  sp_verilog.vh clk_gate.v rvmyth.v rvmyth_gen.v vsdbabysoc.v} -autoread -top vsdbabysoc 
link 
compile_ultra
write_file -format verilog -hierarchy -output /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/output/vsdbabysoc_net.v
report_qor > report_qor.txt
```
![5](https://github.com/user-attachments/assets/ad698170-5a2f-47ec-885c-57289ff991a4)
![6](https://github.com/user-attachments/assets/ea9674cb-7aff-416c-a271-4b5295bcf7b9)
![7](https://github.com/user-attachments/assets/8f387a4d-6b73-440f-bcd6-8e3690258688)
### QOR Report:
![8](https://github.com/user-attachments/assets/62924f0e-fc80-44ff-b387-e8ddbf65be99)
![9](https://github.com/user-attachments/assets/59007962-bf08-4d22-94a4-4e82277318a0)

#### Commands to perform post-synthesis simulation:
```sh
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 -o ./output/post_synth_sim.out ./src/gls_model/primitives.v ./src/gls_model/sky130_fd_sc_hd.v ./output/vsdbabysoc_net.v ./src/module/avsdpll.v ./src/module/avsddac.v ./src/module/testbench.v
cd output
./post_synth_sim.out
gtkwave dump.vcd
```
#### post-synth and pre-synth wave forms are same :
![11](https://github.com/user-attachments/assets/0c5b198d-627a-45fe-bda7-5846d88fc59d)

## Lab - Synthesis with SDC Constraints
### Synthesis using constraints:
In SDC file we have defined the constrains based on the constrains we will synthesis our desing.<br>
Following are the constrains add in the vsdbabysoc_synthesis.sdc file in the folder /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/sdc/<br>
#### Following are the constrains defined in the SDC:
```sh
set_units -time ns
set_max_area 8000
set_load -pin_load 0.5 [get_ports OUT]
set_load -min -pin_load 0.5 [get_ports OUT]
create_clock [get_pins pll/CLK] -name clk -period 10 -waveform {0 5}
set_clock_latency 1 [get_clocks clk]
set_clock_latency -source 2 [get_clocks clk]
set_clock_uncertainty 0.5  [get_clocks clk]
set_max_delay 10 -from [get_pins dac/OUT] -to [get_ports OUT]
set_input_delay -clock clk -max 4 [get_ports VCO_IN]
set_input_delay -clock clk -min 1 [get_ports VCO_IN]
set_input_delay -clock clk -max 4 [get_ports ENb_CP]
set_input_delay -clock clk -min 1 [get_ports ENb_CP]
set_input_transition -max 0.4 [get_ports VCO_IN]
set_input_transition -min 0.1 [get_ports VCO_IN]
set_input_transition -max 0.4 [get_ports ENb_CP]
set_input_transition -min 0.1 [get_ports ENb_CP]
```
### Commands to perform synthesis with SDC constraints:
```sh
dc_shell
set target_library /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.db
set link_library {* /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/sky130_fd_sc_hd__tt_025C_1v80.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsdpll.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsddac.db}
set search_path {/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/include /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/module} 
read_file {sandpiper_gen.vh  sandpiper.vh  sp_default.vh  sp_verilog.vh clk_gate.v rvmyth.v rvmyth_gen.v vsdbabysoc.v} -autoread -top vsdbabysoc 
link
read_sdc /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/sdc/vsdbabysoc_synthesis.sdc
compile_ultra
write_file -format verilog -hierarchy -output /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/output/vsdbabysoc_net_sdc.v
report_qor > report_qor_sdc.txt
report_timing -nets -attributes -input_pins -transition_time -delay_type max > report_setup_sdc.txt
report_timing -nets -attributes -input_pins -transition_time -delay_type min > report_hold_sdc.txt
```
#### Comparing QOR report of the design with and without SDC constraints:
![12](https://github.com/user-attachments/assets/a9cbb0cf-69bb-4d44-a27e-77d61936fb29)
#### Timing report for SETUP with SDC:
```sh
 
****************************************
Report : timing
        -path full
        -delay max
        -input_pins
        -nets
        -max_paths 1
        -transition_time
Design : vsdbabysoc
Version: T-2022.03-SP5-6
Date   : Sat Jul 27 19:56:03 2024
****************************************

Operating Conditions: tt_025C_1v80   Library: sky130_fd_sc_hd__tt_025C_1v80
Wire Load Model Mode: top

  Startpoint: core/CPU_is_addi_a3_reg
              (rising edge-triggered flip-flop clocked by clk)
  Endpoint: core/CPU_Xreg_value_a4_reg[27][31]
            (rising edge-triggered flip-flop clocked by clk)
  Path Group: clk
  Path Type: max

  Des/Clust/Port     Wire Load Model       Library
  ------------------------------------------------
  vsdbabysoc         Small                 sky130_fd_sc_hd__tt_025C_1v80

Attributes:
    d - dont_touch
    u - dont_use
   mo - map_only
   so - size_only
    i - ideal_net or ideal_network
  inf - infeasible path

  Point                                                    Fanout     Trans      Incr       Path      Attributes
  ----------------------------------------------------------------------------------------------------------------------
  clock clk (rise edge)                                                          0.00       0.00
  clock network delay (ideal)                                                    3.00       3.00
  core/CPU_is_addi_a3_reg/CLK (sky130_fd_sc_hd__dfxtp_1)               0.00      0.00       3.00 r
  core/CPU_is_addi_a3_reg/Q (sky130_fd_sc_hd__dfxtp_1)                 0.04      0.29       3.29 f
  core/CPU_is_addi_a3 (net)                                  2                   0.00       3.29 f
  core/U474/A (sky130_fd_sc_hd__nor2_1)                                0.04      0.00       3.29 f
  core/U474/Y (sky130_fd_sc_hd__nor2_1)                                0.12      0.12       3.41 r
  core/n144 (net)                                            2                   0.00       3.41 r
  core/U476/A (sky130_fd_sc_hd__nand2_1)                               0.12      0.00       3.42 r
  core/U476/Y (sky130_fd_sc_hd__nand2_1)                               0.08      0.10       3.52 f
  core/n147 (net)                                            2                   0.00       3.52 f
  core/U9/A (sky130_fd_sc_hd__inv_2)                                   0.08      0.01       3.52 f
  core/U9/Y (sky130_fd_sc_hd__inv_2)                                   0.69      0.52       4.05 r
  core/n150 (net)                                           34                   0.00       4.05 r
  core/U479/B (sky130_fd_sc_hd__xor2_1)                                0.69      0.00       4.05 r
  core/U479/X (sky130_fd_sc_hd__xor2_1)                                0.17      0.19       4.24 f
  core/n210 (net)                                            2                   0.00       4.24 f
  core/U569/A2 (sky130_fd_sc_hd__a21oi_1)                              0.17      0.00       4.24 f
  core/U569/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.25       4.49 r
  core/n809 (net)                                            2                   0.00       4.49 r
  core/U571/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       4.50 r
  core/U571/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       4.61 f
  core/n791 (net)                                            2                   0.00       4.61 f
  core/U574/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       4.62 f
  core/U574/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       4.81 r
  core/n774 (net)                                            2                   0.00       4.81 r
  core/U576/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       4.82 r
  core/U576/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       4.93 f
  core/n755 (net)                                            2                   0.00       4.93 f
  core/U581/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       4.94 f
  core/U581/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       5.14 r
  core/n740 (net)                                            2                   0.00       5.14 r
  core/U583/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       5.14 r
  core/U583/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       5.25 f
  core/n722 (net)                                            2                   0.00       5.25 f
  core/U587/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       5.26 f
  core/U587/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       5.46 r
  core/n707 (net)                                            2                   0.00       5.46 r
  core/U589/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       5.46 r
  core/U589/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       5.57 f
  core/n689 (net)                                            2                   0.00       5.57 f
  core/U344/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       5.58 f
  core/U344/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       5.78 r
  core/n674 (net)                                            2                   0.00       5.78 r
  core/U213/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       5.78 r
  core/U213/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       5.89 f
  core/n656 (net)                                            2                   0.00       5.89 f
  core/U343/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       5.90 f
  core/U343/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       6.10 r
  core/n641 (net)                                            2                   0.00       6.10 r
  core/U210/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       6.10 r
  core/U210/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       6.21 f
  core/n623 (net)                                            2                   0.00       6.21 f
  core/U342/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       6.22 f
  core/U342/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       6.42 r
  core/n608 (net)                                            2                   0.00       6.42 r
  core/U209/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       6.42 r
  core/U209/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       6.53 f
  core/n590 (net)                                            2                   0.00       6.53 f
  core/U341/A1 (sky130_fd_sc_hd__a21oi_1)                              0.08      0.00       6.54 f
  core/U341/Y (sky130_fd_sc_hd__a21oi_1)                               0.20      0.20       6.74 r
  core/n575 (net)                                            2                   0.00       6.74 r
  core/U215/A2 (sky130_fd_sc_hd__o21ai_1)                              0.20      0.00       6.74 r
  core/U215/Y (sky130_fd_sc_hd__o21ai_1)                               0.08      0.11       6.85 f
  core/n557 (net)                                            2                   0.00       6.85 f
  core/U96/A1 (sky130_fd_sc_hd__a21o_1)                                0.08      0.00       6.86 f
  core/U96/X (sky130_fd_sc_hd__a21o_1)                                 0.04      0.17       7.03 f
  core/n541 (net)                                            1                   0.00       7.03 f
  core/U942/CIN (sky130_fd_sc_hd__fa_1)                                0.04      0.01       7.04 f
  core/U942/COUT (sky130_fd_sc_hd__fa_1)                               0.10      0.39       7.43 f
  core/n527 (net)                                            2                   0.00       7.43 f
  core/U94/A1 (sky130_fd_sc_hd__a21o_1)                                0.10      0.00       7.43 f
  core/U94/X (sky130_fd_sc_hd__a21o_1)                                 0.04      0.18       7.61 f
  core/n511 (net)                                            1                   0.00       7.61 f
  core/U905/CIN (sky130_fd_sc_hd__fa_1)                                0.04      0.01       7.62 f
  core/U905/COUT (sky130_fd_sc_hd__fa_1)                               0.08      0.37       7.99 f
  core/n497 (net)                                            1                   0.00       7.99 f
  core/U887/CIN (sky130_fd_sc_hd__fa_1)                                0.08      0.01       8.00 f
  core/U887/COUT (sky130_fd_sc_hd__fa_1)                               0.08      0.38       8.38 f
  core/n965 (net)                                            1                   0.00       8.38 f
  core/U1370/CIN (sky130_fd_sc_hd__fa_1)                               0.08      0.01       8.39 f
  core/U1370/COUT (sky130_fd_sc_hd__fa_1)                              0.09      0.39       8.78 f
  core/n483 (net)                                            1                   0.00       8.78 f
  core/U36/CIN (sky130_fd_sc_hd__fa_2)                                 0.09      0.01       8.79 f
  core/U36/COUT (sky130_fd_sc_hd__fa_2)                                0.08      0.36       9.15 f
  core/n469 (net)                                            2                   0.00       9.15 f
  core/U87/A (sky130_fd_sc_hd__clkinv_1)                               0.08      0.00       9.15 f
  core/U87/Y (sky130_fd_sc_hd__clkinv_1)                               0.03      0.05       9.20 r
  core/n257 (net)                                            1                   0.00       9.20 r
  core/U613/A2 (sky130_fd_sc_hd__o21ai_1)                              0.03      0.01       9.21 r
  core/U613/Y (sky130_fd_sc_hd__o21ai_1)                               0.06      0.06       9.27 f
  core/n452 (net)                                            1                   0.00       9.27 f
  core/U352/CIN (sky130_fd_sc_hd__fa_1)                                0.06      0.01       9.28 f
  core/U352/COUT (sky130_fd_sc_hd__fa_1)                               0.08      0.38       9.65 f
  core/n438 (net)                                            1                   0.00       9.65 f
  core/U348/CIN (sky130_fd_sc_hd__fa_1)                                0.08      0.01       9.66 f
  core/U348/COUT (sky130_fd_sc_hd__fa_1)                               0.08      0.38      10.04 f
  core/n407 (net)                                            1                   0.00      10.04 f
  core/U35/CIN (sky130_fd_sc_hd__fa_1)                                 0.08      0.01      10.05 f
  core/U35/COUT (sky130_fd_sc_hd__fa_1)                                0.08      0.38      10.43 f
  core/n382 (net)                                            1                   0.00      10.43 f
  core/U33/CIN (sky130_fd_sc_hd__fa_1)                                 0.08      0.01      10.44 f
  core/U33/COUT (sky130_fd_sc_hd__fa_1)                                0.10      0.40      10.85 f
  core/n357 (net)                                            2                   0.00      10.85 f
  core/U81/A1 (sky130_fd_sc_hd__a21o_1)                                0.10      0.00      10.85 f
  core/U81/X (sky130_fd_sc_hd__a21o_1)                                 0.04      0.18      11.03 f
  core/n330 (net)                                            1                   0.00      11.03 f
  core/U347/CIN (sky130_fd_sc_hd__fa_1)                                0.04      0.01      11.04 f
  core/U347/COUT (sky130_fd_sc_hd__fa_1)                               0.08      0.37      11.41 f
  core/n305 (net)                                            1                   0.00      11.41 f
  core/U351/CIN (sky130_fd_sc_hd__fa_1)                                0.08      0.01      11.42 f
  core/U351/COUT (sky130_fd_sc_hd__fa_1)                               0.08      0.38      11.80 f
  core/n262 (net)                                            1                   0.00      11.80 f
  core/U617/B (sky130_fd_sc_hd__xor2_1)                                0.08      0.01      11.80 f
  core/U617/X (sky130_fd_sc_hd__xor2_1)                                0.22      0.21      12.02 r
  core/n286 (net)                                            2                   0.00      12.02 r
  core/U618/A (sky130_fd_sc_hd__nand2_2)                               0.22      0.01      12.02 r
  core/U618/Y (sky130_fd_sc_hd__nand2_2)                               0.23      0.19      12.21 f
  core/n284 (net)                                           15                   0.00      12.21 f
  core/U627/B2 (sky130_fd_sc_hd__o22ai_1)                              0.23      0.00      12.21 f
  core/U627/Y (sky130_fd_sc_hd__o22ai_1)                               0.18      0.16      12.37 r
  core/n3166 (net)                                           1                   0.00      12.37 r
  core/CPU_Xreg_value_a4_reg[27][31]/D (sky130_fd_sc_hd__dfxtp_1)      0.18      0.00      12.37 r
  data arrival time                                                                        12.37

  clock clk (rise edge)                                                         10.00      10.00
  clock network delay (ideal)                                                    3.00      13.00
  clock uncertainty                                                             -0.50      12.50
  core/CPU_Xreg_value_a4_reg[27][31]/CLK (sky130_fd_sc_hd__dfxtp_1)              0.00      12.50 r
  library setup time                                                            -0.09      12.41
  data required time                                                                       12.41
  ----------------------------------------------------------------------------------------------------------------------
  data required time                                                                       12.41
  data arrival time                                                                       -12.37
  ----------------------------------------------------------------------------------------------------------------------
  slack (MET)                                                                               0.03


  Startpoint: dac/OUT (internal path startpoint)
  Endpoint: OUT (output port)
  Path Group: default
  Path Type: max

  Des/Clust/Port     Wire Load Model       Library
  ------------------------------------------------
  vsdbabysoc         Small                 sky130_fd_sc_hd__tt_025C_1v80

Attributes:
    d - dont_touch
    u - dont_use
   mo - map_only
   so - size_only
    i - ideal_net or ideal_network
  inf - infeasible path

  Point                        Fanout     Trans      Incr       Path      Attributes
  ------------------------------------------------------------------------------------------
  input external delay                               0.00       0.00 r
  dac/OUT (avsddac)                        0.00      0.00       0.00 r    so 
  OUT (net)                      1                   0.00       0.00 r
  OUT (out)                                0.00      0.87       0.87 r
  data arrival time                                             0.87

  max_delay                                         10.00      10.00
  output external delay                              0.00      10.00
  data required time                                           10.00
  ------------------------------------------------------------------------------------------
  data required time                                           10.00
  data arrival time                                            -0.87
  ------------------------------------------------------------------------------------------
  slack (MET)                                                   9.13


1
```
#### Timing report for HOLD with SDC:
```sh
 
****************************************
Report : timing
        -path full
        -delay min
        -input_pins
        -nets
        -max_paths 1
        -transition_time
Design : vsdbabysoc
Version: T-2022.03-SP5-6
Date   : Sat Jul 27 19:56:20 2024
****************************************

Operating Conditions: tt_025C_1v80   Library: sky130_fd_sc_hd__tt_025C_1v80
Wire Load Model Mode: top

  Startpoint: core/CPU_imm_a2_reg[6]
              (rising edge-triggered flip-flop clocked by clk)
  Endpoint: core/CPU_imm_a3_reg[6]
            (rising edge-triggered flip-flop clocked by clk)
  Path Group: clk
  Path Type: min

  Des/Clust/Port     Wire Load Model       Library
  ------------------------------------------------
  vsdbabysoc         Small                 sky130_fd_sc_hd__tt_025C_1v80

Attributes:
    d - dont_touch
    u - dont_use
   mo - map_only
   so - size_only
    i - ideal_net or ideal_network
  inf - infeasible path

  Point                                          Fanout     Trans      Incr       Path      Attributes
  ------------------------------------------------------------------------------------------------------------
  clock clk (rise edge)                                                0.00       0.00
  clock network delay (ideal)                                          3.00       3.00
  core/CPU_imm_a2_reg[6]/CLK (sky130_fd_sc_hd__dfxtp_1)      0.00      0.00       3.00 r
  core/CPU_imm_a2_reg[6]/Q (sky130_fd_sc_hd__dfxtp_1)        0.04      0.28       3.28 r
  core/CPU_imm_a2[6] (net)                         1                   0.00       3.28 r
  core/CPU_imm_a3_reg[6]/D (sky130_fd_sc_hd__dfxtp_1)        0.04      0.00       3.28 r
  data arrival time                                                               3.28

  clock clk (rise edge)                                                0.00       0.00
  clock network delay (ideal)                                          3.00       3.00
  clock uncertainty                                                    0.50       3.50
  core/CPU_imm_a3_reg[6]/CLK (sky130_fd_sc_hd__dfxtp_1)                0.00       3.50 r
  library hold time                                                   -0.04       3.46
  data required time                                                              3.46
  ------------------------------------------------------------------------------------------------------------
  data required time                                                              3.46
  data arrival time                                                              -3.28
  ------------------------------------------------------------------------------------------------------------
  slack (VIOLATED)                                                               -0.18


1
```
### Commands to perform post-synthesis with SDC constraints:
```sh
cd /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 -o ./output/post_synth_sdc_sim.out ./src/gls_model/primitives.v ./src/gls_model/sky130_fd_sc_hd.v ./output/vsdbabysoc_net_sdc.v ./src/module/avsdpll.v ./src/module/avsddac.v ./src/module/testbench.v
cd output
./post_synth_sdc_sim.out
gtkwave dump.vcd
```
### Wave form of post-synthesis with SDC constraints:
![13](https://github.com/user-attachments/assets/652c3810-bdff-4545-baf9-485e8541a77d)

</details>


<details> 
<summary> Day 14 - Synopsys DC and Timing Analysis </summary>
	
## Synopsys DC and Timing Analysis for different PVT corners
### What is PVT Corners?
PVT Corners refer to the different conditions under which a semiconductor device is tested to ensure it performs reliably across a range of scenarios. PVT stands for Process, Voltage, and Temperature, and the corners represent the extremes of these conditions:<br>

Process Corners: These account for variations in the semiconductor manufacturing process. Since it's impossible to manufacture every chip exactly the same, there are always slight differences. Process corners include:<br>
Typical (T): Represents average conditions in the manufacturing process.<br>
Fast (F): Represents conditions where the manufacturing process resulted in faster than average transistors.<br>
Slow (S): Represents conditions where the manufacturing process resulted in slower than average transistors.<br>
Fast-Slow (F-S): Represents conditions where NMOS transistors are fast and PMOS transistors are slow.<br>
Slow-Fast (S-F): Represents conditions where NMOS transistors are slow and PMOS transistors are fast.<br>

Voltage Corners: These account for variations in the supply voltage. Voltage can vary due to different factors such as power supply quality, load conditions, and environmental factors. Voltage corners include:<br>
Nominal (N): The typical operating voltage.<br>
High (H): A higher than typical operating voltage.<br>
Low (L): A lower than typical operating voltage.<br>

Temperature Corners: These account for variations in the operating temperature. Semiconductors can operate over a range of temperatures, and their performance can vary significantly across this range. Temperature corners include:<br>
Low (L): The lower extreme of the operating temperature range.<br>
Typical (T): Room temperature or the average operating temperature.<br>
High (H): The upper extreme of the operating temperature range.<br>
Testing devices across these corners ensures that they will function correctly under all expected conditions, providing a level of robustness and reliability necessary for most applications.<br>
### Download .lib files for different PVT corners using following repo:
https://github.com/efabless/skywater-pdk-libs-sky130_fd_sc_hd/tree/master/timing
### Script to convert .lib to .db format:
### Write a shell script to invoke lc_shell and execute tcl script
```sh
#run_convert.sh
#!/bin/sh

LC_SHELL_PATH="/usr/synopsys/lc/T-2022.03-SP5/bin/lc_shell"
TCL_SCRIPT="convert_lib_to_db.tcl"

$LC_SHELL_PATH -f $TCL_SCRIPT
```
### Write a tcl script to convert all .lib files to .db
```sh
# convert_lib_to_db.tcl
set lib_files_dir "/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/Timing/timing";
set db_output_dir "/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/all_db_files";

foreach lib_file [glob -nocomplain $lib_files_dir/*.lib] {
    set base_name [file rootname [file tail $lib_file]]
    set db_file "$db_output_dir/${base_name}.db"

    if {[llength [list_libs]] > 0} {
        remove_lib [lindex [list_libs] 0]
    }

    read_lib $lib_file

    write_lib $base_name -format db -output $db_file

    if {[llength [list_libs]] > 0} {
        remove_lib [lindex [list_libs] 0]
    }
}

exit
```
### Script to perform synthesis with SDC constraints with multi PVT corners:
### Write a shell script to invoke dc_shell and execute tcl script
```sh
# run_dc_pvt_corners.sh
#!/bin/bash

TCL_SCRIPT_PATH="/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/script/timing_multi_pvt_corners.tcl"
LOG_FILE="dc_shell.log"
dc_shell -f $TCL_SCRIPT_PATH | tee $LOG_FILE
```
### Write a tcl script to perform synthesis with SDC constraints with multi PVT corners
```sh
# timing_multi_pvt_corners.tcl
set file_handle [open report_timing.rpt w]
puts $file_handle "PVT_Corner\tWNS\tWHS"

set lib_files [glob -directory /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/Timing/timing/ -type f *.db]

foreach lib_file_paths $lib_files {

regexp {.*\/sky130_fd_sc_hd__(.*)\.db$} $lib_file_paths full_match pvt_corners

set timing_report_fast_mode true

set target_library $lib_file_paths
set link_library {* /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsdpll.db /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/lib/avsddac.db}
lappend link_library $target_library
set search_path {/home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/include /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/module}
read_file {sandpiper_gen.vh  sandpiper.vh  sp_default.vh  sp_verilog.vh clk_gate.v rvmyth.v rvmyth_gen.v vsdbabysoc.v} -autoread -top vsdbabysoc
source /home/bhaskar/vsd/VSDBabySOC/VSDBabySoC/src/sdc/vsdbabysoc_synthesis.sdc
link
compile_ultra

set wns [get_attribute [get_timing_paths -delay_type max -max_paths 1] slack]
set whs [get_attribute [get_timing_paths -delay_type min -max_paths 1] slack]

puts $file_handle "$pvt_corners\t$wns\t$whs"

reset_design
}

close $file_handle
exit
```
### Below table explians Worst Negative/Setup Slack (WNS) & Worst Hold Slack (WHS) for different PVT corners for BabySoC Design :
| PVT_Corner    |      WNS   |      WHS   |
| ------------- | -----------| -----------|
| ff_100C_1v65  | 0.00459766 | -0.244979  |
| ff_100C_1v95  | 0.227859   | -0.298619  |
| ff_n40C_1v56  | 0.0493441  | -0.201714  |
| ff_n40C_1v65  | 0.0182953  | -0.23863   |
| ff_n40C_1v76  | 0.032217   | -0.269796  |
| ff_n40C_1v95  | 0.0913324  | -0.307088  |
| ss_100C_1v40  | 0.00604248 | 0.413952   |
| ss_100C_1v60  | 1.7014     | 0.14934    |
| ss_n40C_1v28  | -2.14636   | 1.2782     |
| ss_n40C_1v35  | 0.00161362 | 0.825907   |
| ss_n40C_1v40  | 0.00352478 | 0.607227   |
| ss_n40C_1v44  | 0.00133705 | 0.498978   |
| ss_n40C_1v60  | 0.00631809 | 0.169568   |
| ss_n40C_1v76  | 0.00544834 | -0.0055871 |
| tt_025C_1v80  | 0.198813   | -0.184026  |
| tt_100C_1v80  | 0.00269318 | -0.179197  |

![1](https://github.com/user-attachments/assets/63f82541-ecef-4859-b6e8-57c7d148e9f4)

![3](https://github.com/user-attachments/assets/042fcce9-d583-4fdf-a87b-4119f6cab4c2)

![4](https://github.com/user-attachments/assets/87d71ae7-3275-423e-a0d2-d1793af41ed7)

![5](https://github.com/user-attachments/assets/9a9ca48a-846f-455d-9c21-0032213e4139)

### Based on the above report table we need to select the PVT corners that represent the worst-case scenarios for both Worst Negative Slack (WNS) and Worst Hold Slack (WHS). Here are the steps to identify the PVT corners:
### 1. Identify the worst-case WNS:
Worst-case WNS is the most negative WNS value, which indicates the scenario where the setup time is most critical.
### 2. Identify the worst-case WHS:
Worst-case WHS is the most negative WHS value, which indicates the scenario where the hold time is most critical.

### Analysis of the Table
### For WNS:
The most negative WNS value is -2.14636 at the PVT corner ss_n40C_1v28.
### For WHS:
The most negative WHS value is -0.307088 at the PVT corner ff_n40C_1v95.

### Selected PVT Corners for Analysis
### 1. Worst-case Setup Timing (WNS):
PVT Corner: ss_n40C_1v28 with WNS of -2.14636.
### 2. Worst-case Hold Timing (WHS):
PVT Corner: ff_n40C_1v95 with WHS of -0.307088.<br>

These PVT corners should be considered for detailed timing analysis to ensure that the design meets the required setup and hold times under the most critical conditions.
</details>





<details> 
<summary> Day 15 - Physical Design Basics </summary>
<ul>
<details> 
<summary> OpenLANE EDA Tool </summary>	
	
## OpenLANE EDA Tool
### Introduction to open source EDA, OpenLANE and sky 130 PDK:
In this for study we are taking ARDUINO board as example where we can able to see a chip.<br>
![1](https://github.com/user-attachments/assets/3e445de8-ae13-4d04-b205-3d429091a456)<br>
The outer part what we are able to see is an package (Quad Flat NO-leads). Within that chip is at center where it is connect to the pins through wire bonds to comunicate with signals coming from out side.<br>
![4](https://github.com/user-attachments/assets/47039779-aa51-4157-beda-bb8de40e6795)<br>
Chip contains a pads and is used to commuicate to out side world. And the core of the chip where our actual digital logics sits.<br>
![6](https://github.com/user-attachments/assets/504d9607-cc10-4c24-9081-d96100041df4)<br>
![7](https://github.com/user-attachments/assets/4f845edd-ecce-43b7-b8e8-d8c7509c297a)<br>
In a chip it contains IP's macros.<br>
### IP(Intellectual Property):
VLSI IP refers to pre-designed and pre-verified circuit blocks or design modules that can be licensed and reused in different chip designs. These IP blocks can range from simple functions like arithmetic units to complex systems like entire processors or communication interfaces.<br>
### Types of VLSI IP<br>
#### Soft IP: 
These are typically provided in the form of synthesizable HDL (Hardware Description Language) code, such as VHDL or Verilog. They offer flexibility but may require further synthesis, place and route, and verification.

#### Hard IP: 
These are provided as layout designs, which are fully placed and routed and are specific to a particular fabrication process. They are less flexible but offer faster integration and potentially better performance.

#### Firm IP: 
These lie between soft and hard IP. They are partially synthesized and may come with specific constraints but still allow some flexibility in optimization for different processes.

### Macros:
macros refer to pre-designed, reusable logic blocks or modules that are used to implement specific functions within an integrated circuit (IC). They are similar to IP (Intellectual Property) blocks but can vary in terms of complexity and the stage of design abstraction.<br>
#### Types of Macros in VLSI
#### Standard Cell Macros:

These are basic logic gates (AND, OR, NOT, etc.), flip-flops, and other simple circuits that are used as the building blocks for more complex designs. Standard cells are typically part of a standard cell library provided by semiconductor companies.
#### Hard Macros:

These are pre-designed and pre-verified blocks that are provided in a fixed layout format. They are specific to a particular process technology and are used to implement critical functions like memory blocks (e.g., SRAM, ROM) or complex analog circuits. Hard macros are less flexible in terms of modification but offer optimized performance and reliability.
#### Soft Macros:

These are described in a high-level hardware description language (HDL) like Verilog or VHDL. They are more flexible and can be synthesized and optimized for different technology nodes. Soft macros are typically used for functional blocks where customization or optimization for different applications is required.
#### Firm Macros:

These are partially synthesized and come with specific constraints. They offer a balance between flexibility and optimization, allowing some level of customization while still providing a partially optimized layout.
### Introduction to RISC-V Instruction Set Architecture (ISA):
If we want to run C program on an hardwear initially the C program is comipled in assambly language which is then converted in to binary language.
And also we need to implement RISC-V processor architecture using Hardware description language based on the specification.
![9](https://github.com/user-attachments/assets/77ce7b1d-1817-4ea5-a084-9f55c70c7bf8)

### From softwear application to Hardwear:
How the application softwear's like PDF rader, Microsoft Excell are run on hrdwear through a series of steps involving in the system softwear. System softwear contains different components like Oprating system(OS), Compiler, and Assembled.
Whre the application are written in the Java,C,C++ these are compiled and converted into instructions based on the hardwear if hardware is RISC-V compiler will convert's into RISC-V format instruction set. And Assembler will convert instruction set in to binary means meachine readable formt.
![9](https://github.com/user-attachments/assets/34536629-5cd4-4c08-ac7d-379fafd5705a)
![10](https://github.com/user-attachments/assets/8b01f281-9ec4-4179-ad89-9b0a906314fd)
![11](https://github.com/user-attachments/assets/3b504b3e-4634-4569-a3a5-eea7b986cb54)
![13](https://github.com/user-attachments/assets/db494edd-f139-41b9-aa94-476241906b52)
## SOC Design and OpenLANE:
### Digital ASIC design:
To design ASIC based design we are using RTL IP's, EDA tools and PDK. Here we are using EDA tool is OpenLANE.<br>
### PDK( PDK stands for Process Design Kit):
A PDK is a comprehensive collection of files and data that provide the necessary information and resources for designing integrated circuits (ICs) using a specific semiconductor manufacturing process. It is provided by semiconductor foundries to ensure that designers can create designs that are manufacturable and meet the performance and reliability specifications of the process technology.<br>
### Key Components of a PDK:
#### Technology Files:
Define the process technology's parameters, such as layer stack, design rules, and process variations.
Include information on the physical and electrical characteristics of the semiconductor process.

#### Design Rules:
A set of constraints and guidelines that must be followed during the design process to ensure manufacturability.
Include minimum width, spacing, and enclosure rules for different layers and features.

#### Device Models:
Provide SPICE (Simulation Program with Integrated Circuit Emphasis) models for transistors, capacitors, resistors, and other devices used in the process.
Include parameters for different operating conditions and process corners (e.g., typical, slow, fast).

#### Standard Cell Libraries:
Pre-designed and characterized logic gates and flip-flops that are used as building blocks in digital design.
Include timing, power, and area information for each cell.

#### IO Libraries:
Pre-designed input/output (IO) cells that facilitate communication between the chip and the external world.
Include different types of IO cells, such as general-purpose IOs, power pads, and analog interfaces.

#### Memory Compilers:
Tools and libraries for generating customized memory blocks (e.g., SRAM, ROM) based on specific requirements.
Include different configurations and performance parameters.

#### Analog and Mixed-Signal Components:
Pre-designed analog and mixed-signal blocks, such as operational amplifiers, ADCs (Analog-to-Digital Converters), and DACs (Digital-to-Analog Converters).
Include characterization data for performance verification.
![16](https://github.com/user-attachments/assets/363ec634-5810-4c4e-bb44-d03d4859c499)
## RTL To GDSII Flow:
![18](https://github.com/user-attachments/assets/f93387fd-dc82-48d2-87f1-dc2547a54c52)
### Synthesis
The RTL code is transformed into a gate-level netlist using synthesis tools. The gate level net list is functional equivalent to RTL design.
![19](https://github.com/user-attachments/assets/7b36e398-75e5-4e5f-b9ad-1b94d3ec17ed)
![20](https://github.com/user-attachments/assets/a8d48cd8-7a35-4844-8a89-7e90fc84712e)
#### Tools: 
Synopsys Design Compiler, Cadence Genus, Mentor Graphics Precision.
## Floorplanning/Power Planning:
Define the physical organization of the chip by determining the placement of major functional blocks. Design the power distribution network to ensure adequate power delivery to all parts of the chip and power distribution is done using higher matel layer as compre to lower metal layer.
![21](https://github.com/user-attachments/assets/561ce03b-902e-4df6-8962-527057aeee2c)
![22](https://github.com/user-attachments/assets/0270c7f0-236b-40e7-b060-6816348783a0)
![23](https://github.com/user-attachments/assets/6cc622c5-1524-4f23-8814-beec21903202)
## Placement:
Place the standard cells and macros within the floorplan whre pacement done in two steps.<br>
![24](https://github.com/user-attachments/assets/6b4c3665-a8a9-4fab-aa11-8750de86bed0)
### 1. Global placement.
Where the standard cells and macros (functional blocks) are placed on the chip's floorplan. The goal is to determine the approximate locations means cells are not legally posistioned.<br>
![25](https://github.com/user-attachments/assets/079c923a-2b77-4297-b9a9-39725192f4dc)
### 2. Detailed placements.
Where the standard cells and macros (functional blocks) are placed on the chip's floorplan and are legally posistioned in the placement rows.<br>
![26](https://github.com/user-attachments/assets/746f8f73-c108-4406-a3c9-3f42b8547e68)
## Clock Tree Synthesis (CTS):
Design the clock distribution network to ensure synchronized operation of sequential elements.
![27](https://github.com/user-attachments/assets/c7724204-f3ae-455f-9b9a-d1d4a8438a20)
## Routing:
Create the metal interconnections between placed cells.
![28](https://github.com/user-attachments/assets/ddfb1532-42c9-4c9b-a799-c23fc6752d23)
![29](https://github.com/user-attachments/assets/33519af8-9b79-4552-bb52-d4c4b931c749)
## Sign-Off:
This refers to the final stage of the design process where the design is thoroughly checked and verified before it is sent to the foundry for fabrication.
![30](https://github.com/user-attachments/assets/db3564a6-32c7-4d3d-8c69-50722a90f908)
## Introduction to OpenLANE:
![31](https://github.com/user-attachments/assets/4a49f0ad-2c43-41c8-95d2-703bfe09df76)
![32](https://github.com/user-attachments/assets/b19174aa-6e40-4658-ac6c-71a2f1a682e5)
![33](https://github.com/user-attachments/assets/12b99479-21c2-4419-a2e7-7e488e54e6c8)
![34](https://github.com/user-attachments/assets/103656b9-78d3-4827-b1c6-2a311defa2a3)
![35](https://github.com/user-attachments/assets/41180b2c-1990-460e-8933-8fbdfecc6059)
## Introduction to OpenLANE ASIC Flow:
![38](https://github.com/user-attachments/assets/1f97c5d2-5f21-438c-94b3-cb6b6ddafb8d)
### Tools and Technologies in OpenLane:
![40](https://github.com/user-attachments/assets/19d08e0e-1ab0-428d-98e7-4a29217c04e8)
#### Yosys: 
Open-source synthesis tool used for converting RTL to a gate-level netlist.
![42](https://github.com/user-attachments/assets/34b9e8ea-5896-4464-8591-9bd5dbc27bd0)
#### OpenROAD: 
A suite of open-source tools for physical design, including placement, CTS, and routing.
![41](https://github.com/user-attachments/assets/30236e25-a914-4fac-9fcb-b44e61ceab13)
#### Magic: 
Open-source layout tool used for physical verification.
#### OpenSTA: 
Static Timing Analysis tool for verifying timing constraints.
#### Fault: 
![39](https://github.com/user-attachments/assets/088ecbdb-c97c-4cd7-946c-1f52cdc8eb7c)
</details> 
<details> 
<summary> OpenLANE EDA Tool Flowand LAB </summary>
<ul>
<details> 
<summary> Design Prepration </summary>
	
## Design Prepration setup:
To perform design prepration setup and invoke the openlane excute the folowing command
```sh
cd /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane
alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
```
</details>
<details> 
<summary> Run Synthesis </summary>
	
## Run Synthesis for picorv32a design using openlane flow
To run the synthesis use the following command
```sh
run_synthesis
```
![43](https://github.com/user-attachments/assets/0e910450-0fa2-4867-87a7-dc4aaa4f920c)
### Chartacterize the synthesis results:
![44](https://github.com/user-attachments/assets/d802bc91-c584-4060-aca9-dc2d538f0614)
#### Flop ratio:
Flop Ratio = (Total number of DFF’s)/(Total number of standard cells)=1613/14876=0.108429
### Synthesised Netlist:
![45](https://github.com/user-attachments/assets/3fcd93f6-2deb-470b-81a6-e14885ec079c)
![46](https://github.com/user-attachments/assets/c29c05bf-2dfe-45ef-b16d-be926d502f7b)
</details>
<details> 
<summary> Floor Plan </summary>

## Floor Plan
Floor planning is the proccess of defining die area, core area, plcing of input and out ports, power planning and macro placement.<br>
1. Initialization of a floorplan of appropriate dimension means defining width and height of the core and die area.<br>
2. Macro Placement measn defining location of the preplaced cell's.<br>
3. Placement of endcap cells means suround preplaced cell's with decoupling cells.<br>
4. Power planning.<br>
5. Placement of I/O pins.<br>
6. Applying appropriate placement blockages near the I/O pins.<br>

### Switch Avilable in openlane for floorplan:
![35](https://github.com/user-attachments/assets/b380d27a-e91f-4625-b6e4-635afafccb71)
### These are the default Switch set to floorplan:
![36](https://github.com/user-attachments/assets/ac212825-5996-416b-9c34-cd11a6399245)

1. These are system default settings and it is the lowest precedence that is "floorplan.tcl" vailable in the folder "/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/configuration".<br>
2. Then next precedence will be "config.tcl" in the project folder "/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a".<br>
3. Then next precedence will be "sky130A_sky130_fd_sc_hd_config.tcl" in the project folder "/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a".<br>
### Run the command for floorplan:
```sh
run_floorplan
```
### Magic tool to open floorplan:
### Command to open floorplan:
```sh
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
![37](https://github.com/user-attachments/assets/37d8452b-e008-4a79-b9cf-76f0cc9b6ac6)
#### In Magic tool to see which metal is used for horizonatal and vertical pin:
![38](https://github.com/user-attachments/assets/a395dd61-2be2-4c64-b541-2ef61e175790)
#### In Magic tool we can see TAP cell and DECAP cell's:
![39](https://github.com/user-attachments/assets/64c72dda-69ba-4a13-b86a-027dbf9feda8)
#### Still placement of standard cell's not done in floor plan:
![40](https://github.com/user-attachments/assets/79ee2209-d77e-43ea-b7a4-a7fd33ba40bb)

</details>
<details> 
<summary> Placement and Routing </summary>

## Placement
### Placement Algorithms:
#### Global Placement: 
In this initial step, cells are roughly placed to provide a good starting point for more detailed placement. The focus is on spreading the cells across the die evenly and avoiding high congestion areas.
#### Detailed Placement: 
After global placement, cells are fine-tuned to their exact positions to optimize timing, power, and area further. Detailed placement resolves any overlaps and fine-tunes cell positions for better performance.<br>

To performed the placement of standard cell's use following command.<br>
```sh
run_placement
```
### Command to open placement:
```sh
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
![49](https://github.com/user-attachments/assets/e480976f-6795-4f91-8c8d-86c998589a55)
![50](https://github.com/user-attachments/assets/382017ea-c2aa-43ac-a739-eb3c1c1c2603)

</details>

<details> 
<summary> IO Placer </summary>
	
In Openlane we IO placer can be used to place the IO pins by setting switch FP_IO_MODE.
### Command to set to switch FP_IO_MODE and view floorplan using Magic tool:
```sh
set ::env(FP_IO_MODE) 2
run_floorplan
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
![8](https://github.com/user-attachments/assets/03e3091c-4129-4b07-a6eb-5f21033cca91)

</details>

<details> 
<summary> Standard cell design </summary>

## Standard cell design and characterization using openlane
```txt
cd /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane
git clone https://github.com/nickson-jose/vsdstdcelldesign.git
copy sky130A tech file into /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
cd /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic
cp sky130A.tech /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/
cd /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
```
![22](https://github.com/user-attachments/assets/97a983e3-bcef-4026-8973-bbffe26d74a3)

</details>
</ul>
</details> 
<details> 
<summary> Chip Floor Planning </summary>

## Floor Planning
The first step of physical design is defining width and height of the core and die.
### 1. How to the value of values of w(width) and h(height):
If we concider the simple netlist where we have FF(flip-flops/latch's/register's) and standard cells.<br>
To calculate the width and height of the core and die first we should know the dimention of the standard cells, as of now we concider only dimention of standard cells not the wires.<br>
![Screenshot 2024-08-10 171853](https://github.com/user-attachments/assets/341890ba-1cdc-45e7-8390-f60f5528a862)
![2](https://github.com/user-attachments/assets/c78a3032-b6d4-4c5f-b705-27e80c53f54d)
![3](https://github.com/user-attachments/assets/5008932c-4848-433c-b40f-7ee14e6d4c60)
![4](https://github.com/user-attachments/assets/96f7e32a-40df-4437-bde8-47fa3b50531d)
![5](https://github.com/user-attachments/assets/8ebd77bd-4b9d-4fb2-9e36-1e218e668a2f)

If we take area occupied by standard cells of netlist is 4sq unit and total are of the core will be 2sq unit by 2sq unit means 4sq unit.<br>
![5_A](https://github.com/user-attachments/assets/27e303ff-cde9-4e98-a32b-113cd5c7ab8d)
![6](https://github.com/user-attachments/assets/f5fa56aa-d9ec-4c83-8513-bf3bb2210ae4)
![7](https://github.com/user-attachments/assets/285ed8aa-e23e-4eda-b780-29900800f37c)
![8](https://github.com/user-attachments/assets/3fbc3811-bd56-47c7-962c-9e7583cc713e)

Here standart cell's of netlist utlizes 100% of core area so utilization factor will be of 1.<br>
Means there should be some space for other logic and routing.<br>

### Aspect Ration:
Acspect ratio is Height/Width of the core when the aspect ratio is one it tells that the chip is square shape. If the aspect ratio is less then 1 it says the chip is rectangler.<br>
![10](https://github.com/user-attachments/assets/aeb419ba-8fbd-414d-a7c2-03e7fe3ddc63)<br>
If we take another example with different core area. Where the utilization factor is 0.5 and aspect ratio will be 0.5.<br>
If utilization factor is 0.5 that indicates 50% of the core is utilized by standard cells of the netlist and other 50% is utilized by other logic and routing.<br>
If aspect ratio is 0.5 indicates the chip is rectangler.<br>
![12](https://github.com/user-attachments/assets/3eb76712-05da-4292-af64-2391d184a1e3)

### Another example:
![13](https://github.com/user-attachments/assets/ffb0e70d-5a44-44d4-a52a-d83a91585665)
### Preplaced cell's:
Generally the netlist contain complex logic is partitioned into multiple blocks.<br>
![14](https://github.com/user-attachments/assets/0f0d926c-95f0-4e1c-9aad-d356ac6565a3)
![15](https://github.com/user-attachments/assets/e723eb84-870a-4f5d-98ba-b7d9675a9451)

These blocks are indipendently implemented as reusable blocks. It means it is implemented once and reused multiple times.<br>
![16](https://github.com/user-attachments/assets/a6975774-d60b-4bec-a3e2-114a2acab341)

Preplaced cells are a type of structural element in physical design, particularly in electronics and integrated circuit (IC) fabrication.<br>
They are pre-designed and pre-fabricated cells that can be easily incorporated into a larger design, reducing the complexity and time required for layout and verification. These are called IP's are resusable blocks these are call prelaced cells.<br>
![17](https://github.com/user-attachments/assets/14b8ee3d-f217-4f28-829b-634a33d8f8b5)

### 2. Defining location of preplaced cell's:
The location of the preplaced is decided based on the design requirement.<br>
Like if blocks talk to the inputs pins so we need to to place blocks near to the input pin's so it's depends on the design requirement.<br>
![18](https://github.com/user-attachments/assets/49898afe-84a6-4a59-958e-65a44731c715)

### 3. Surround preplaced cell's with decoupling cells:
![19](https://github.com/user-attachments/assets/bc7fa579-dec6-414e-af0d-45509057cae7)

In the circuit as shown above when the gates switches/transition from zero to one the capacitance has to charge to represent logic one. The amount of charge is passed from vdd/supply voltage.<br>
In the same way when gate switches/transition from one to zero the capacitance has to discharge to represent logic zero. VSS take that amout of charge to discharge the capacitor.<br>
If thre is a larg distance between the voltage source and the design there may be chance of voltage drop due to some pysical dimessions.<br> 
If the voltage drop is within the noise margin then its fine or if voltage drop is more then it leads to indetermined state of transition.<br>
![20](https://github.com/user-attachments/assets/7bfac4dd-9711-4be8-8bfb-a6a3dfc77b07)

To over come that issue we need to use decoupling capacitance. The voltage accros the capacitor is similer to the poer supply.<br>
The decopuling capacitors decouples the circuit from the main supply.<br>
Decoupling cell's are added only for critical block's not for all the clock's.<br>

![21](https://github.com/user-attachments/assets/4fbf12c1-a861-45e2-9b51-ac107fb0d217)
![22](https://github.com/user-attachments/assets/4474122c-2d61-4988-8b73-f514a2081f6f)


### 4. Power Planning:
For local communication decoupling capacitor is fine for global commnication we resolve the issue with power planning.
![23](https://github.com/user-attachments/assets/b8aa1cff-c598-4a2b-8d1b-22d981d009bc)

Indted of providing one power supply from on place we can have multiple power dupply. This can be implemented by power mesh it will supply the power nearest logic.
![27](https://github.com/user-attachments/assets/2e2157d8-6734-4562-a975-8271e83beb10)
![28](https://github.com/user-attachments/assets/f1f2c77f-f3c7-4233-ab65-3f79ef8be612)

### 5. Pin placement:
Lets concider a design below there will be multiple input and output ports.<br>

![29](https://github.com/user-attachments/assets/2c17df48-bad2-4050-ac92-63cf9f44713f)
![30](https://github.com/user-attachments/assets/125bbc16-32c7-4319-b937-4e03fdb839f0)

It has connectivity of the different gates from different port's. This connectivity of the netlist are defined using verilog.<br>
![31](https://github.com/user-attachments/assets/fd264ce9-9796-4efd-8742-953fc6663b26)

Here the pin placement is differe from design to design and the size of the clock port is bigger as compare to data port.<br>
![32](https://github.com/user-attachments/assets/4602d090-276b-4942-8c37-216c90a8d8aa)

These clock port drives flop's in the complete design so size is biger and lower in recistence.<br>

### 6. Logical cell's placement blockage:
placement blockage is the area where the cells must avoid during placement, optimization and legalization. It can be hard and soft.<br>
The placement of these blockeg is to avoid to take care the tool should not place other cell's near the port's.<br>
![33](https://github.com/user-attachments/assets/a6425002-3485-4bff-b0d9-2c7276ae01b9)

</details>
<details> 
<summary> Place and routing </summary>

## Place and routing
### 1. Bind netlist with physical cells:
Bind netlist with physical cells is the process of mapping a logical cell (like logic gate, flip-flop, or other standard cell) to a specific physical cell in the standard cell library during the physical design phase.<br>
#### Cell Libraries: 
Standard cell libraries contain pre-designed physical layouts for logic gates, flip-flops, and other basic components used in digital design. Each logic cell has multiple implementations (different sizes and power characteristics) to cater to different design constraints.

#### Logical to Physical Mapping: 
After the synthesis step, where the RTL (Register Transfer Level) code is converted into a gate-level netlist, each logical cell in the netlist needs to be associated with a corresponding physical cell from the library.

#### Constraints Consideration:
##### Timing Constraints: 
Cells are selected based on their ability to meet the timing requirements of the design.
##### Power Constraints: 
Cells are chosen to minimize power consumption, especially in low-power designs.
##### Area Constraints: 
The physical size of the cell is also a consideration, as it impacts the overall chip area.
![41](https://github.com/user-attachments/assets/4c013bc1-a401-45a3-9ae9-38f3f964ba7d)

The library is classified into two one it contains shape and size and another library contains the delay information.<br>
In the library there are different size and of same types cell's means AND gate of different size of cell's avilable in the library.<br>
Where bigger cell have faster as compare to smaller cell's.<br>
![42](https://github.com/user-attachments/assets/68c58c08-92f1-461b-b950-d84ac946a61a)

### 2. Placement: 
Once the cells are bound, the physical design process continues with placement, placement is a crucial step in the physical design flow. It involves positioning the standard cells (like logic gates, flip-flops, and other basic components) into cell boundry.<br>
At placment stage already pre placed cell should not affeted mean's preplaced cell's must be fixed they should not move.<br>
There is no cell's placed in that area where the preplaced cell's are placed.<br>
![43](https://github.com/user-attachments/assets/ad71fee9-810f-4654-be49-849fa1ed6765)

Hrere the cell's are placed based on port which are commnicatting with the ports.<br>
And based on the which are communicatting with other preplaced cell's.<br>
![45](https://github.com/user-attachments/assets/c4ac446a-4021-49ad-8eff-53881798286c)

Some cell's are placed for away brom each other related to one logic. The solution to this is optimize placment.
### 3. Optimize placment: 
In this stage where we estimate wire length and capacitance and, based on that insert reapeaters here repeaters are bufferes.<br>
These repeaters are used to reproduce the original signal and send these repeaters come into picute where wire lenthg is high but there will be loss of area. <br>
![46](https://github.com/user-attachments/assets/b6308b0d-a710-4ef2-bf89-6d7d82fc82ff)
![47](https://github.com/user-attachments/assets/7f7d3e08-99b5-4650-acbe-5f2af975a957)
![48](https://github.com/user-attachments/assets/223050f6-838b-4260-8bbc-2ad45cf378ea)

Here the clocks are not build by concidering clock path as ideal it means clock to reach any of the flip flop is zero is the ideal clock. So we need to check timing for the data path.<br>
</details>
<details> 
<summary> Cell design and characterization flow </summary>
	
## Cell design flow
The information of the standard cell's are avilable in the library.<br>
Library contains different flavors of same standard cells like cell's with different size and with different functinality(AND, OR, Inverter etc...) of cell's.<br>
Based on the size of the cell they different threshold voltage bigers cells have high threshold voltage.<br>
![53](https://github.com/user-attachments/assets/9de008bd-c59d-4f40-87c4-ae9f672e9b54)

The cell design flow is divided into 3 part's.
1. Inputs.
2. Design flow.
3. Outputs.

### 1. Inputs:
Inputs to design the inverter we required proccess deign kits.<br>
These kits are provided by foundry and the kits consists of DRC (Design rul check's), LVS (Layout Versus Schematic) rules, SPICE models, library and user defined specs.<br>
DRC's are the design rules provided by foundry to design the cell's some of are.<br>
Poly width.<br>
extension over active.<br>
poly to active spacing.<br>
![54](https://github.com/user-attachments/assets/4fcb9407-b5dd-4bf3-9931-68c8016a69d4)

SPICE models also provided by foundry based on the equation provided foundry parameters.<br>
![55](https://github.com/user-attachments/assets/126f2125-2f4f-4cff-9e30-c5b186fd71a7)

Library and user defined specs is also provided by foundry and user defined specs are cell height, supply voltage, meta layers, pin location, drwan gate length.

### 2. Design flow's:
Design involves 3 different step's.<br>
1. Circuit design.<br>
2. Layout design.<br>
3. Characterization.<br>

#### 1. Circuit design:
Circuit design involves two steps.<br>
1) Implement the function.<br>
2) Model PMOS and NMOS transister based on the library requirement.<br>
The output we get from the circuit design is the CDL (circuit description launguage) file.

#### 2. Layout design:
First implementing a function.<br>
Deriving pmos and nmos network graph done.<br>

![58](https://github.com/user-attachments/assets/e99adbe9-eae2-496b-9f70-f620029bec04)

Obtain the Euler's path. Euler's path is the path traced only once.<br>

![59](https://github.com/user-attachments/assets/fa66e78d-759f-4ac9-b8b1-237ec115c286)

Based on the Euler's path draw the stick diagram and make the connection based on the circuit.<br>
Then convert stick diagram into layout based on the based on the rules provided by foundy.<br>
![60](https://github.com/user-attachments/assets/0aef694e-d3f0-49f5-ba9d-9ad01012e170)

Extract parasitics from the layout and characterize interms of timing.<br>

The output of layout deisgn is GDSII , LEF(where have information on height and width of the cell), extracted spice netlist(.cir).
#### 3. Characterization:
We need to charaterize baed on the extracted spice netlist, sub circuits(it contains the information of NMOS and PMOS SPICE models).<br>
Characterization setup.<br>
1. Reading the models.
2. Reading the extracted SPICE nestlist.
3. Recognise the behaviour of the design.
4. Read sub circuits of the design.
5. Attach the nessary power source.
6. Applay the stimulus.
7. Provide the nessary output load capacitance.
8. Provide nessary simulation command.

Feed the all inputs in the form of configuration to the tool(GUNA).<br>
Then this tool generates Timing, Noice, Power .lib's function.<br>


</details>

<details> 
<summary> Timing chracterization </summary>
	
## Timing chracterization
### Slew:
Time taken for a signal to increase from 20% to 80% of its maximum value for raise time, time it takes for a signal to decrease from 80% to 20% of its maximum value for fall time is call slew.<br>
**slew_low_rise_thr**<br>
**slew_high_rise_thr**<br>
**slew_low_fall_thr**<br>
**slew_high_fall_thr**<br>
### Transition Time:
![7](https://github.com/user-attachments/assets/53bd81fb-f6d4-4890-bdec-a57315c79fc1)
```text
slew raise = time(slew_high_rise_thr) - time(slew_low_rise_thr)
slew fall = time(slew_high_fall_thr) - time(slew_low_fall_thr)
If 80% vdd is 1.44v and 20% of vdd is 036v
input slew is 26ps output slew 54ps from above transition wave form
```
### Propagation delay:
Propagation delay is typically measured from the 50% point of the input signal's transition to the 50% point of the output signal's transition.<br>
**in_rise_thr**<br>
**in_fall_thr**<br>
**out_rise_thr**<br>
**out_fall_thr**<br>
```text
PT = time(out_*_thr) - time(in_*_thr)
If in_rais_thr = 3.207ns and out_fall_thr = 3.230ns
PT = 3.230ns - 3.207ns = 23ps
If in_rais_thr = 3.263ns and out_fall_thr = 3.221ns
PT = 3.221ns - 3.263ns = -42ps
This -ve indicates out put comes before the input.
Due to input delay there may be chance of getting -ve delay.
```
</details>

<details> 
<summary> SPICE Deck creation for CMOS Inverter </summary>

## SPICE Deck creation for CMOS Inverter
### SPICE Deck:
1. Connectivity information about the netlist.
2. Define the component values.
	Define channel length and width of the channel.
	Define the output load.
	Define the input gate voltage.
	Define drain voltage or mainsupplay voltage.
![9](https://github.com/user-attachments/assets/39eecb92-f107-4953-bef2-7a4e331574d6)
4. Identify 'nodes': The points between there is a componet.
5. Name Node's.

![11](https://github.com/user-attachments/assets/78a2587f-8a5f-4945-88f3-23cd38e552f5)

#### SPICE Deck Defination:
```text
M1 out in vdd vdd pmos W=0.375u L=0.25u
Nothing but below is the description
M1 drain gate source substrate pmos width length
```
The .mod file contain the all the technology related parameter's.
![14](https://github.com/user-attachments/assets/30317f99-a128-423c-90a2-735ff510f220)

By sweeping gate input voltage from 0v to 2.5v at steps of 0.05v

We are going to perfom SPICE simulation for the following parameters.
![15](https://github.com/user-attachments/assets/5a6b6cf0-eafc-49da-ad6d-0a8a8e9f60f2)

#### Switching threshold:
Switching threshold is the point where Vin = Vout the gate voltage is equal to drain voltage Vgs=Vds where current IdsP=IdsN.<br>
This is the point where the both the switches are turned on so there will leakage current.<br>
And Current directly can flow from power to ground.<br>
![15](https://github.com/user-attachments/assets/8a7d390c-75c4-431e-b7b3-f517d838ed4d)

</details>
<details> 
<summary> Inception of layout and CMOS fabrication </summary>

## Inception of layout and CMOS fabrication
### 16 Mask CMOS Process:
1. Selecting of substrate.<br>
The commonly used subrate is P-type silicon substrate it has high resistivity, dooping level, orientation.<bt>
Substrate dooping should be less than well dooping.<br>
![24](https://github.com/user-attachments/assets/7d1346d1-769c-4e44-a04a-789390f0e9b4)

2. Creating active region for transistor.<br>
	Step 1: Grow a 40nm of Silicon dioxide over a P-substrate it act as insulator.<br>
	![25](https://github.com/user-attachments/assets/8999d682-8764-4ebe-bc54-c106002029a1)

	Step 2: Deposite a layer of 80nm of silicon nitride over a Silicon dioxide.<br>
	![26](https://github.com/user-attachments/assets/1fefe49a-ac2d-49cc-8c7c-fd9ae5691b3a)

   	Step 3: Deposite a layer of 1um photoresist(where photoresist is a filme).<br>
	![27](https://github.com/user-attachments/assets/f5e0e0c1-1b85-46db-ae9b-45a49bde6480)

   	Step 4: Create the Mask1 (Layout's are converted into mask) by expossing to UV light this is nothing but photo lithography.<br>
   	![28](https://github.com/user-attachments/assets/47d37a09-6b8a-4be5-98d5-5021d055d0ac)

   	Steo 5: Remove the unexposed area to UV light.<br>
   	![29](https://github.com/user-attachments/assets/48b236af-da07-4dc9-82ea-83fe473b62cb)

 	Step 6: Remove the mask.<br>
	![30](https://github.com/user-attachments/assets/653a7bcc-38ba-4ee7-ac74-36c6e2be173c)

   	Step 7: Etching of silicon nitride where the area unexposed to UV light.<br>
    	![31](https://github.com/user-attachments/assets/e643bdad-b470-4bcb-b22e-3501ef3aae2a)

 	Step 8: Remove the photoresist chemically.<br>
  	![32](https://github.com/user-attachments/assets/bbb6b4b1-cd4f-49ee-aa9c-876eafaec306)

   	Step 9: Growth of oxidation by keeping in oxidation furnace. Field oxidation is grow and this is called "LOCOS"(Local Oxidation Of Silicon).<br>
	![33](https://github.com/user-attachments/assets/1df51134-3ed9-41ad-a489-6d076b69ab25)

	Step 10: Etching of silicon nitride.<br>
 	![34](https://github.com/user-attachments/assets/505db23e-7eb6-42c0-82f1-134f27d5f23f)

3. N-Well and P-Well formation.<br>
 	Step 1: Deposite a layer of photoresist.<br>
  	![35](https://github.com/user-attachments/assets/da7357ab-d2b6-4623-91b5-5d262919d27e)

 	Step 2: Create the Mask2 and expose to UV light.<br>
  	![37](https://github.com/user-attachments/assets/de584d7e-a3ce-42af-8498-608dc94885e5)

 	Step 3: Remove the mask.<br>
  	![38](https://github.com/user-attachments/assets/b704dc35-e0db-40b9-b5f8-307dbf93ead0)

 	Step 4: Create a P-Well using a Boron is an P-type material and it is difussed into P-type substrate using a process called Ion Implantation.<br>
  	![39](https://github.com/user-attachments/assets/ec97a85e-3a24-4947-a5fe-3330e6883568)

   	Step 5: Repeate the above steps 1 and 2 proces with Mask3.<br>
    	![40](https://github.com/user-attachments/assets/c5ae6585-3f71-44bd-9e4a-6f3d03ab45c2)

 	Step 6: Create a N-Well using a Phosphorous is an N-type material and it is difussed into P-type substrate to create N-Well.<br>
  	![41](https://github.com/user-attachments/assets/168071b9-e653-45b1-bf89-9c8f1c1dc490)

 	Step 7: Diffuse Boron and Phosphorous into P-type substrate to create clear P-Well and N-Well.<br>
  	![43](https://github.com/user-attachments/assets/c98e75c2-f878-4d90-99bd-8d8fdf55bbfa)

 	
</details>
</ul>
</details>
