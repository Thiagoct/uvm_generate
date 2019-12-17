bloco = xxx
#bloco2 = xxx
top:
	@echo "module top;" >> ../../tb/top.sv
	@echo "   import uvm_pkg::*;" >> ../../tb/top.sv
	@echo "   import pkg::*;" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv	
	@echo "   // Sinais de Controle" >> ../../tb/top.sv
	@echo "   logic          clk;" >> ../../tb/top.sv
	@echo "   logic          rst;" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	@echo "   //Instanciar a interface e conexões" >> ../../tb/top.sv
	#-----------------------------instanciar interfaces abaixo---------------------
	@echo "   ${bloco}_if dut_${bloco}_if" >> ../../tb/top.sv
	@echo "   (" >> ../../tb/top.sv
	@echo "      .clk        (clk)," >> ../../tb/top.sv
	@echo "      .rst      (rst)" >> ../../tb/top.sv
	@echo "   );" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	#-----------------------------segunda interface--------------------------------
	#@echo "   ${bloco2}_if dut_${bloco2}_if" >> ../../tb/top.sv
	#@echo "   (" >> ../../tb/top.sv
	#@echo "      .clk        (clk)," >> ../../tb/top.sv
	#@echo "      .rst      (rst)" >> ../../tb/top.sv
	#@echo "   );" >> ../../tb/top.sv

	#------------------------------------------------------------------------------
	@echo " " >> ../../tb/top.sv
	@echo "   //Instanciar o dut e suas conexões" >> ../../tb/top.sv
	#-----------------------------instanciar dut abaixo----------------------------
	

	#------------------------------------------------------------------------------
	@echo " " >> ../../tb/top.sv
	@echo "   initial begin"​ >> ../../tb/top.sv
	@echo "      clk = 1;​" >> ../../tb/top.sv
	@echo "      rst = 1;"​ >> ../../tb/top.sv
	@echo "      #20 rst = 0;​ //verificar com a equipe se o reset vai ser esse mesmo" >> ../../tb/top.sv
	@echo "      #20 rst = 1;​" >> ../../tb/top.sv
	@echo "   end​" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	@echo "   always #10 clk = !clk;​ //verificar com a equipe se o clk vai ser esse" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	@echo "   initial begin​" >> ../../tb/top.sv
	@echo "      \`ifdef XCELIUM​" >> ../../tb/top.sv
	@echo "      \$recordvars();​" >> ../../tb/top.sv
	@echo "      \`endif​" >> ../../tb/top.sv
	@echo "      \`ifdef VCS"​ >> ../../tb/top.sv
	@echo "      \$vcdpluson;​" >> ../../tb/top.sv
	@echo "      \`endif​" >> ../../tb/top.sv
	@echo "      \`ifdef QUESTA"​ >> ../../tb/top.sv
	@echo "      \$wlfdumpvars();"​ >> ../../tb/top.sv
	@echo "      set_config_int("*", "recording_detail", 1);" >> ../../tb/top.sv​
	@echo "      \`endif"​ >> ../../tb/top.sv
	@echo "   end" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	@echo "   initial begin //Inserir as interfaces aqui (setar elas)"
	@echo "      uvm_config_db#(virtual ${bloco}_if)::set(uvm_root::get(), \"*\", \"vif\", dut_alu_if); //trocar vif pelo nome da interface virutal no driver" >> ../../tb/top.sv
	#------------------------------------Para mais de uma interface-----------------
	#@echo "      uvm_config_db#(virtual ${bloco_2}_if)::set(uvm_root::get(), \"*\", \"vif\", dut_reg_if);" >> ../../tb/top.sv
	#-------------------------------------------------------------------------------
	@echo "   end" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	@echo "   initial begin" >> ../../tb/top.sv
	@echo "      run_test("simple_test");"​ >> ../../tb/top.sv
	@echo "   end" >> ../../tb/top.sv
	@echo " " >> ../../tb/top.sv
	@echo "endmodule : top" >> ../../tb/top.sv