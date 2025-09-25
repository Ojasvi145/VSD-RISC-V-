# Week1 Day5: If case , for loop & for generate statements
## IF CASE

### Incomp_if

```bash
$ iverilog incomp_if.v tb_incomp_if.v
$ ./a.out
$ gtkwave tb_incomp_if.vcd
```
![Alt text](IMAGES/2.png)

```bash
$yosys
yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib           
yosys> read_verilog incomp_if.v                                                 
yosys> synth -top incomp_if                                         
yosys> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> write_verilog -noattr incomp_if_net.v                
yosys> show 
```
![Alt text](IMAGES/1.png)

### Incomp_if2

```bash
$ iverilog incomp_if.v tb_incomp_if2.v
$ ./a.out
$ gtkwave tb_incomp_if2.vcd
```
![Alt text](IMAGES/3.png)

```bash
$yosys
yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib           
yosys> read_verilog incomp_if2.v                                                 
yosys> synth -top incomp_if2                                         
yosys> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> write_verilog -noattr incomp_if2_net.v                
yosys> show 
```
![Alt text](IMAGES/4.png)

## CASE STATEMENTS
### Incomp_case

```bash
$ iverilog incomp_case.v tb_incomp_case.v
$ ./a.out
$ gtkwave tb_incomp_case.vcd
```
![Alt text](IMAGES/5.png)

```bash
$yosys
yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib           
yosys> read_verilog incomp_case.v                                                 
yosys> synth -top incomp_case                                      
yosys> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> write_verilog -noattr incomp_case_net.v                
yosys> show 
```
![Alt text](IMAGES/6.png)

### comp_case

```bash
$ iverilog comp_case.v tb_comp_case.v
$ ./a.out
$ gtkwave tb_comp_case.vcd
```
![Alt text](IMAGES/8.png)

```bash
$yosys
yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib           
yosys> read_verilog comp_case.v                                                 
yosys> synth -top comp_case                                      
yosys> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> write_verilog -noattr comp_case_net.v                
yosys> show 
```
![Alt text](IMAGES/7.png)

### bad_case

```bash
$ iverilog bad_case.v tb_bad_case.v
$ ./a.out
$ gtkwave tb_bad_case.vcd
```
![Alt text](IMAGES/9.png)
![Alt text](IMAGES/10.png)

## FOR ..LOOP AND FOR ..GENERATE STATEMENTS
### mux_generate

```bash
$ iverilog mux_generate.v tb_mux_generate.v
$ ./a.out
$ gtkwave tb_mux_generate.vcd
```
![Alt text](IMAGES/11.png)

```bash
$yosys
yosys> read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib           
yosys> read_verilog mux_generate.v                                                 
yosys> synth -top mux_generate                                      
yosys> abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> write_verilog -noattr mux_generate_net.v                
yosys> show 
```
![Alt text](IMAGES/12.png)
![Alt text](IMAGES/13.png)

## FOR ..GENERATE STATEMENTS
### fa.v rca.v
![Alt text](IMAGES/16.png)
![Alt text](IMAGES/17.png)

### demux_case
![Alt text](IMAGES/18.png)
![Alt text](IMAGES/19.png)
![Alt text](IMAGES/20.png)

### demux_generate
![Alt text](IMAGES/21.png)
![Alt text](IMAGES/22.png)
![Alt text](IMAGES/23.png)



