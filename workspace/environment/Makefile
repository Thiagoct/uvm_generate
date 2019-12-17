block = xxx
#bloco2 = xxx 
n_testes = 10000

coverage:
	
	@echo "class coverage extends uvm_component;" >> ../../tb/coverage.sv
	@echo " \`uvm_component_utils(coverage)"​ >> ../../tb/coverage.sv
	@echo " " >> ../../tb/coverage.sv
	#-----------------------------intanciação das transactions------------------------------
	@echo "  ${block}_transaction ${block}_tr;​" >> ../../tb/coverage.sv
	@echo "  uvm_analysis_imp#(${block}_transaction, coverage) ${block}_port;​" >> ../../tb/coverage.sv
	#---------------------------------------------------------------------------------------
	@echo "  int min_tr;​" >> ../../tb/coverage.sv
	@echo "  int n_tr = 0;"​ >> ../../tb/coverage.sv
	#-------------------------------------declaração de eventos-----------------------------
	#exemplo @echo "  event end_of_simulation;"​ >> ../../tb/coverage.sv


	#---------------------------------------------------------------------------------------
	@echo "  event end_of_simulation;"​ >> ../../tb/coverage.sv
	@echo " " >> ../../tb/coverage.sv
	@echo "  function new(string name = "coverage", uvm_component parent= null);"​ >> ../../tb/coverage.sv
	@echo "    super.new(name, parent);​" >> ../../tb/coverage.sv
	@echo "    ${block}_port = new("${block}_port", this);​" >> ../../tb/coverage.sv
	@echo "    ${block}_tr=new;​" >> ../../tb/coverage.sv
	#-----------------------------------alterar para mais transactions----------------------


	#---------------------------------------------------------------------------------------
	@echo "    min_tr = ${n_testes};​" >> ../../tb/coverage.sv
	@echo "  endfunction​" >> ../../tb/coverage.sv
	@echo " " >> ../../tb/coverage.sv
	@echo "	 function void build_phase(uvm_phase phase);" >> ../../tb/coverage.sv
	@echo "    super.build_phase (phase);​" >> ../../tb/coverage.sv
	@echo "  endfunction​" >> ../../tb/coverage.sv
	@echo " " >> ../../tb/coverage.sv
	@echo "  task run_phase(uvm_phase phase);​" >> ../../tb/coverage.sv
	@echo "    phase.raise_objection(this);​" >> ../../tb/coverage.sv
	@echo "    @(end_of_simulation);​" >> ../../tb/coverage.sv
	@echo "    phase.drop_objection(this);"​ >> ../../tb/coverage.sv
	@echo "  endtask: run_phase​" >> ../../tb/coverage.sv
	@echo " " >> ../../tb/coverage.sv
	@echo "  function void write(${block}_transaction t);" >> ../../tb/coverage.sv
	#------------------------------alterar para caso de handshake----------------------------
	#exemplo @echo "​     if(t.valid_out) begin" >> ../../tb/coverage.sv
	

	#----------------------------------------------------------------------------------------
	@echo "        n_tr = n_tr + 1;​" >> ../../tb/coverage.sv
	@echo "        if(n_tr >= min_tr)begin"​ >> ../../tb/coverage.sv
	@echo "           ->end_of_simulation;​" >> ../../tb/coverage.sv
	@echo "        end​" >> ../../tb/coverage.sv
	@echo "     end" >> ../../tb/coverage.sv
	@echo "  endfunction: write"​ >> ../../tb/coverage.sv
	@echo " " >> ../../tb/coverage.sv 
	@echo "endclass : coverage" >> ../../tb/coverage.sv

environment:
	@echo "class environment extends uvm_env;" >> ../../tb/environment.sv
	@echo " \`uvm_component_utils(environment)" >> ../../tb/environment.sv
	@echo " " >> ../../tb/environment.sv
	@echo "  ${block}_agent   	${block}_agt;" >> ../../tb/environment.sv
	#------------------------------para mais de um agent--------------------------------
	#@echo "  ${block2}_agent   	${block2}_agt;" >> ../../tb/environment.sv
	#-----------------------------------------------------------------------------------
	@echo "  scoreboard  	sb;" >> ../../tb/environment.sv
	@echo "  coverage    	cov;" >> ../../tb/environment.sv
	@echo " " >> ../../tb/environment.sv
	@echo "  function new(string name = \"environment\", uvm_component parent = null);" >> ../../tb/environment.sv​
	@echo "     super.new(name, parent);​" >> ../../tb/environment.sv
	@echo "  endfunction: new​" >> ../../tb/environment.sv
	@echo " " >> ../../tb/environment.sv	
	@echo "  virtual function void build_phase(uvm_phase phase);" >> ../../tb/environment.sv
	@echo "     super.build_phase(phase);" >> ../../tb/environment.sv
	@echo "     ${block}_agt = ${block}_agent::type_id::create (\"${block}_agt\", this);" >> ../../tb/environment.sv
	#------------------------------para mais de um agent--------------------------------
	#@echo "     ${block2}_agt = ${block2}_agent::type_id::create(\"${block2}_agt\", this);" >> ../../tb/environment.sv
	#-----------------------------------------------------------------------------------
	@echo "     sb = scoreboard::type_id::create(\"sb\", this);" >> ../../tb/environment.sv
	@echo "     cov = coverage::type_id::create(\"cov\", this);" >> ../../tb/environment.sv
	@echo "  endfunction : build_phase" >> ../../tb/environment.sv
	@echo " " >> ../../tb/environment.sv	
	@echo "  virtual function void connect_phase(uvm_phase phase);" >> ../../tb/environment.sv
	@echo "     ${block}_agt.${block}_agt_port.connect(cov.${block}_port); // ${block}_agt -> coverage" >> ../../tb/environment.sv
	@echo "     ${block}_agt.${block}_agt_port.connect(sb.${block}_mon_port); // ${block}_agt -> refmod" >> ../../tb/environment.sv
	@echo "     ${block}_agt.ref_agt_port.connect(sb.${block}_ref_port); // ${block}_agt -> comp" >> ../../tb/environment.sv
	#------------------------------para mais de um agent--------------------------------
	#@echo "     ${block2}_agt.${block2}_agt_port.connect(sb.${block2}_mon_port); // ${block2}_agt -> refmod" >> ../../tb/environment.sv
	#-----------------------------------------------------------------------------------
	@echo "  endfunction : connect_phase" >> ../../tb/environment.sv
	@echo " " >> ../../tb/environment.sv	
	@echo "endclass : environment" >> ../../tb/environment.sv		