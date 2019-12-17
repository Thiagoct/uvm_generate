bloco = xxx
#bloco2 = xxx
teste:
	@echo "class simple_test extends uvm_test;" >> ../../tb/simple_test.sv
	@echo "  \`uvm_component_utils(simple_test)" >> ../../tb/simple_test.sv
	@echo " " >> ../../tb/simple_test.sv
	@echo "    environment	 env;" >> ../../tb/simple_test.sv
	@echo "    ${bloco}_sequence	 ${bloco}_seq;" >> ../../tb/simple_test.sv
	#-------------------------------------para mais de um sequence---------------------------
	#@echo "    ${bloco2}_sequence	 ${bloco2}_seq;" >> ../../tb/simple_test.sv
	#----------------------------------------------------------------------------------------
	@echo " " >> ../../tb/simple_test.sv
	@echo "    function new(string name = \"simple_test\", uvm_component parent = null);"​ >> ../../tb/simple_test.sv
	@echo "       super.new(name, parent);​" >> ../../tb/simple_test.sv
	@echo "    endfunction: new​" >> ../../tb/simple_test.sv
	@echo " " >> ../../tb/simple_test.sv	
	@echo "    virtual function void build_phase(uvm_phase phase);" >> ../../tb/simple_test.sv
	@echo "       super.build_phase(phase);" >> ../../tb/simple_test.sv
	@echo "       env = environment::type_id::create(\"env\", this);" >> ../../tb/simple_test.sv
	@echo "       ${bloco}_seq = ${bloco}_sequence::type_id::create(\"${bloco}_seq\", this);" >> ../../tb/simple_test.sv
	#-------------------------------------para mais de um sequence------------------------------
	#@echo "       ${bloco2}_seq = ${bloco2}_sequence::type_id::create(\"${bloco2}_seq\", this);" >> ../../tb/simple_test.sv
	#----------------------------------------------------------------------------------------
	@echo "    endfunction : build_phase" >> ../../tb/simple_test.sv
	@echo " " >> ../../tb/simple_test.sv	
	@echo "    task run_phase(uvm_phase phase);" >> ../../tb/simple_test.sv
	@echo "       fork" >> ../../tb/simple_test.sv
	@echo "          ${bloco}_seq.start(env.${bloco}_agt.${bloco}_sqr);" >> ../../tb/simple_test.sv
	#-------------------------------------para mais de um bloco------------------------------
	#@echo "          ${bloco2}_seq.start(env.${bloco2}_agt.${bloco2}_sqr);" >> ../../tb/simple_test.sv
	#----------------------------------------------------------------------------------------
	@echo "       join" >> ../../tb/simple_test.sv       
	@echo "    endtask : run_phase" >> ../../tb/simple_test.sv
	@echo " " >> ../../tb/simple_test.sv	
	@echo "endclass: simple_test" >> ../../tb/simple_test.sv