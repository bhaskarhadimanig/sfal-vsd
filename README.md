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
