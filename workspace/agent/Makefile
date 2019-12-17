block = xxx

transaction:
	@echo "class ${block}_transaction extends uvm_sequence_item;" >> ../../tb/${block}_transaction.sv
	@echo "//Entradas do DUT" >> ../../tb/${block}_transaction.sv
	@echo " " >> ../../tb/${block}_transaction.sv
	#---------------------------Alterar com as entradas do DUT--------------------------
	#exemplo @echo "rand bit [15:0] sinal;" >> ../../tb/${block}_transaction
	
	
	#-----------------------------------------------------------------------------------
	@echo " " >> ../../tb/${block}_transaction.sv
	@echo "//Saídas do DUT" >> ../../tb/${block}_transaction.sv	
	@echo " " >> ../../tb/${block}_transaction.sv
	#---------------------------Alterar com as saídas do DUT----------------------------
	#exemplo @echo "bit [15:0] sinal;" >> ../../tb/${block}_transaction
	

	#-----------------------------------------------------------------------------------	
	@echo " " >> ../../tb/${block}_transaction.sv
	@echo "//Construtor" >> ../../tb/${block}_transaction.sv
	@echo "function new (string name = \"${block}_transaction\");" >> ../../tb/${block}_transaction.sv
	@echo "	  super.new(name);" >> ../../tb/${block}_transaction.sv
	@echo "endfunction // new" >> ../../tb/${block}_transaction.sv	
	@echo " " >> ../../tb/${block}_transaction.sv
	@echo "// Macros" >> ../../tb/${block}_transaction.sv
	@echo "\`uvm_object_param_utils_begin(${block}_transaction)" >> ../../tb/${block}_transaction.sv
	#--------------------------Alterar com as entradas do DUT---------------------------
	#exemplo @echo "   \`uvm_field_int(data_in, UVM_UNSIGNED)" >> ../../tb/${block}_transaction.sv
	

	#-----------------------------------------------------------------------------------
	#--------------------------Alterar com as saidas do DUT-----------------------------
	#exemplo @echo "   \`uvm_field_int(data_out, UVM_UNSIGNED)" >> ../../tb/${block}_transaction.sv
	

	#-----------------------------------------------------------------------------------
	@echo "\`uvm_object_utils_end" >> ../../tb/${block}_transaction.sv
	@echo " " >> ../../tb/${block}_transaction.sv
	@echo "endclass // ${block}_transaction" >> ../../tb/${block}_transaction.sv


sequence:
	@echo "class ${block}_sequence extends uvm_sequence #(${block}_transaction);" >> ../../tb/${block}_sequence.sv 
	@echo "     \`uvm_object_utils(${block}_sequence)" >> ../../tb/${block}_sequence.sv 
	@echo " " >> ../../tb/${block}_sequence.sv
	@echo "     function new(string name = \"${block}_sequence\");" >> ../../tb/${block}_sequence.sv 
	@echo "        super.new(name);" >> ../../tb/${block}_sequence.sv 
	@echo "     endfunction: new" >> ../../tb/${block}_sequence.sv 
	@echo " " >> ../../tb/${block}_sequence.sv	
	@echo "     task body();" >> ../../tb/${block}_sequence.sv 
	@echo "        ${block}_transaction tr;" >> ../../tb/${block}_sequence.sv  
	@echo "        forever begin" >> ../../tb/${block}_sequence.sv 
	@echo "           tr = ${block}_transaction::type_id::create(\"tr\");" >> ../../tb/${block}_sequence.sv 
	@echo "           start_item(tr);" >> ../../tb/${block}_sequence.sv 
	@echo "           assert(tr.randomize());" >> ../../tb/${block}_sequence.sv 
	@echo "           finish_item(tr);" >> ../../tb/${block}_sequence.sv 
	@echo "        end" >> ../../tb/${block}_sequence.sv 
	@echo "     endtask: body" >> ../../tb/${block}_sequence.sv 
	@echo "endclass: ${block}_sequence" >> ../../tb/${block}_sequence.sv 


driver:
	@echo "typedef virtual ${block}_if ${block}_vif;" >> ../../tb/${block}_driver.sv 
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "class ${block}_driver extends uvm_driver #(${block}_transaction);" >> ../../tb/${block}_driver.sv
	@echo "   \`uvm_component_utils(${block}_driver)" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   ${block}_vif vif;" >> ../../tb/${block}_driver.sv
	@echo "   ${block}_transaction tr;" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   function new(string name = \"${block}_driver\", uvm_component parent = null);" >> ../../tb/${block}_driver.sv
	@echo "      super.new(name, parent);" >> ../../tb/${block}_driver.sv
	@echo "   endfunction // new;" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   virtual function void build_phase(uvm_phase phase);" >> ../../tb/${block}_driver.sv
	@echo "      super.build_phase(phase);" >> ../../tb/${block}_driver.sv
	@echo "      if(!uvm_config_db#(${block}_vif)::get(this, \"\", \"vif\", vif))" >> ../../tb/${block}_driver.sv
	@echo "         \`uvm_fatal(\"NOVIF\", \"failed to get virtual interface\")" >> ../../tb/${block}_driver.sv
	@echo "   endfunction // build_phase" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   task run_phase(uvm_phase phase);" >> ../../tb/${block}_driver.sv
	@echo "        fork" >> ../../tb/${block}_driver.sv 
	@echo "           reset_signals();" >> ../../tb/${block}_driver.sv
	@echo "           get_and_drive(phase);" >> ../../tb/${block}_driver.sv
	@echo "        join" >> ../../tb/${block}_driver.sv
	@echo "   endtask // run_phase" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   virtual task reset_signals();" >> ../../tb/${block}_driver.sv
	@echo "      wait(vif.rst === 0);" >> ../../tb/${block}_driver.sv
	@echo "      forever begin" >> ../../tb/${block}_driver.sv
	#-------------------------------Alterar com o sinais a serem resetados-----------------------
	#exemplo @echo "vif.valid_in <= 0;" >> ../../tb/${block}_driver.sv

	#--------------------------------------------------------------------------------------------
	@echo "         @(negedge vif.rst);" >> ../../tb/${block}_driver.sv
	@echo "      end" >> ../../tb/${block}_driver.sv
	@echo "   endtask // reset_signals" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   virtual task get_and_drive(uvm_phase phase);" >> ../../tb/${block}_driver.sv
	@echo "      wait (vif.rst === 0);" >> ../../tb/${block}_driver.sv
	@echo "      @(posedge vif.rst);" >> ../../tb/${block}_driver.sv
	@echo "      forever begin" >> ../../tb/${block}_driver.sv
	@echo "         seq_item_port.get_next_item(tr);" >> ../../tb/${block}_driver.sv
	@echo "         driver_transfer(tr);" >> ../../tb/${block}_driver.sv
	#---------------------------------Alterar para handshake-------------------------------------
	#exemplo @echo "if(vif.valid_in) wait(vif.valid_out);" >> ../../tb/${block}_driver.sv


	#--------------------------------------------------------------------------------------------
	@echo "         seq_item_port.item_done();" >> ../../tb/${block}_driver.sv
	@echo "      end" >> ../../tb/${block}_driver.sv
	@echo "   endtask // get_and_drive" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "   virtual task driver_transfer(${block}_transaction tr);" >> ../../tb/${block}_driver.sv
	@echo "      @(posedge vif.clk);" >> ../../tb/${block}_driver.sv
	#----------Alterar para atribuição de valores da transaction para a interface virtual--------
	#exemplo @echo "      vif.data_A   <= tr.data_in;" >> ../../tb/${block}_driver.sv
	#exemplo flag de entrada @echo "      vif.valid_in <= '1';" >> ../../tb/${block}_driver.sv


	#--------------------------------------------------------------------------------------------
	@echo "   endtask // driver_transfer" >> ../../tb/${block}_driver.sv
	@echo " " >> ../../tb/${block}_driver.sv
	@echo "endclass // ${block}_driver" >> ../../tb/${block}_driver.sv

monitor:
	@echo "class ${block}_monitor extends uvm_monitor;" >> ../../tb/${block}_monitor.sv
	@echo "    \`uvm_component_utils(${block}_monitor)" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   ${block}_vif vif;" >> ../../tb/${block}_monitor.sv
	@echo "   ${block}_transaction ${block}_tr;" >> ../../tb/${block}_monitor.sv
	#------------------Alterar para a instanciação de mais interfaces ou transactions----------


	#------------------------------------------------------------------------------------------
	@echo "   ref_transaction ref_tr;" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   uvm_analysis_port #(${block}_transaction) ${block}_mon_port;" >> ../../tb/${block}_monitor.sv
	@echo "   uvm_analysis_port #(ref_transaction) ref_mon_port;" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   function new(string name = \"${block}_monitor\", uvm_component parent = null);" >> ../../tb/${block}_monitor.sv
	@echo "      super.new(name, parent);" >> ../../tb/${block}_monitor.sv
	@echo "      ${block}_mon_port = new(\"${block}_mon_port\", this);" >> ../../tb/${block}_monitor.sv
	#------------------------------Alterar para mais transactions------------------------------


	#------------------------------------------------------------------------------------------
	@echo "      ref_mon_port = new(\"ref_mon_port\", this);" >> ../../tb/${block}_monitor.sv
	@echo "   endfunction // new" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   virtual function void build_phase(uvm_phase phase);" >> ../../tb/${block}_monitor.sv
	@echo "      super.build_phase(phase);" >> ../../tb/${block}_monitor.sv
	@echo "      if(!uvm_config_db#(${block}_vif)::get(this, \"\", \"vif\", vif))" >>  ../../tb/${block}_driver.sv
	@echo "        \`uvm_fatal(\"NOVIF\", \"failed to get virtual interface\")" >> ../../tb/${block}_monitor.sv
	@echo "         ${block}_tr = ${block}_transaction::type_id::create(\"${block}_tr\", this);" >> ../../tb/${block}_monitor.sv 
	#------------------------------Alterar para mais transactions------------------------------


	#------------------------------------------------------------------------------------------
	@echo "         ref_tr = ref_transaction::type_id::create(\"ref_tr\", this);" >> ../../tb/${block}_monitor.sv
	@echo "   endfunction // build_phase" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   virtual task run_phase(uvm_phase phase);" >> ../../tb/${block}_monitor.sv
	@echo "      super.run_phase(phase);" >> ../../tb/${block}_monitor.sv
	@echo "      fork" >> ../../tb/${block}_monitor.sv
	@echo "         collect_${block}_transaction(phase);" >> ../../tb/${block}_monitor.sv
	#------------------------------Alterar para mais transactions------------------------------


	#------------------------------------------------------------------------------------------
	@echo "         collect_ref_transaction(phase);" >> ../../tb/${block}_monitor.sv
	@echo "      join" >> ../../tb/${block}_monitor.sv
	@echo "   endtask // run_phase" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   virtual task collect_${block}_transaction(uvm_phase phase);" >> ../../tb/${block}_monitor.sv
	@echo "      forever begin" >> ../../tb/${block}_monitor.sv
	@echo "         @(posedge vif.clk);" >> ../../tb/${block}_monitor.sv
	@echo "         if(vif.rst) begin" >> ../../tb/${block}_monitor.sv
	@echo "            begin_tr(${block}_tr, \"${block}_tr\");" >> ../../tb/${block}_monitor.sv
	#-------------Alterar para as transanctions receberem valor da interface virtual------------
	#exemplo @echo "alu_tr.data_in   = vif.data_in;" >> ../../tb/${block}_monitor.sv 

	#-------------------------------------------------------------------------------------------
	@echo "            ${block}_mon_port.write(${block}_tr);" >> ../../tb/${block}_monitor.sv
	@echo "            @(negedge vif.clk);" >> ../../tb/${block}_monitor.sv
	@echo "            end_tr(${block}_tr);" >> ../../tb/${block}_monitor.sv
	@echo "         end " >> ../../tb/${block}_monitor.sv
	@echo "      end // forever begin" >> ../../tb/${block}_monitor.sv
	@echo "   endtask // collect_transaction" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "   virtual task collect_ref_transaction(uvm_phase phase);" >> ../../tb/${block}_monitor.sv
	@echo "      forever begin" >> ../../tb/${block}_monitor.sv
	@echo "         @(posedge vif.clk);" >> ../../tb/${block}_monitor.sv
	#-------------------------Alterar para condição de coleta e retirar o #---------------------
	
	#@echo "         if() begin" >> ../../tb/${block}_monitor.sv

	#-------------------------------------------------------------------------------------------
	@echo "            begin_tr(ref_tr, \"ref_tr\");" >> ../../tb/${block}_monitor.sv
	#-------------------------Alterar para Saidas do DUT----------------------------------------
	#exemplo @echo "            ref_tr.data_out = vif.data_out;" >> ../../tb/${block}_monitor.sv
	@echo "            ref_mon_port.write(ref_tr);" >> ../../tb/${block}_monitor.sv
	@echo "            @(negedge vif.clk);" >> ../../tb/${block}_monitor.sv
	@echo "            end_tr(ref_tr);" >> ../../tb/${block}_monitor.sv
	@echo "         end" >> ../../tb/${block}_monitor.sv
	@echo "      end" >> ../../tb/${block}_monitor.sv
	@echo "   endtask // collect_ref_transaction" >> ../../tb/${block}_monitor.sv
	@echo " " >> ../../tb/${block}_monitor.sv
	@echo "endclass // ${block}_monitor" >> ../../tb/${block}_monitor.sv

agent:
	@echo "typedef uvm_sequencer#(${block}_transaction) ${block}_sequencer;" >> ../../tb/${block}_agent.sv  
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "class ${block}_agent extends uvm_agent;" >> ../../tb/${block}_agent.sv 
	@echo "  \`uvm_component_utils(${block}_agent)" >> ../../tb/${block}_agent.sv
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "   ${block}_sequencer ${block}_sqr;" >> ../../tb/${block}_agent.sv
	@echo "   ${block}_driver ${block}_drv;" >> ../../tb/${block}_agent.sv
	@echo "   ${block}_monitor ${block}_mon;" >> ../../tb/${block}_agent.sv
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "   uvm_analysis_port #(${block}_transaction) ${block}_agt_port;" >> ../../tb/${block}_agent.sv
	#-------------------------Alterar para mais transactions-------------------------------------


	#--------------------------------------------------------------------------------------------
	@echo "   uvm_analysis_port #(ref_transaction) ref_agt_port;" >> ../../tb/${block}_agent.sv
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "   function new(string name = \"${block}_agent\", uvm_component parent = null);" >> ../../tb/${block}_agent.sv
	@echo "      super.new(name, parent);" >> ../../tb/${block}_agent.sv
	@echo "      ${block}_agt_port = new(\"${block}_agt_port\", this);" >> ../../tb/${block}_agent.sv
	#-------------------------Alterar para mais transactions-------------------------------------

	
	#--------------------------------------------------------------------------------------------
	@echo "      ref_agt_port = new(\"ref_agt_port\", this);" >> ../../tb/${block}_agent.sv
	@echo "   endfunction // new" >> ../../tb/${block}_agent.sv
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "   virtual function void build_phase(uvm_phase phase);" >> ../../tb/${block}_agent.sv
	@echo "      super.build_phase(phase);" >> ../../tb/${block}_agent.sv
	@echo "      ${block}_sqr = ${block}_sequencer::type_id::create(\"${block}_sqr\", this);" >> ../../tb/${block}_agent.sv
	@echo "      ${block}_drv = ${block}_driver::type_id::create(\"${block}_driver\", this);" >> ../../tb/${block}_agent.sv
	@echo "      ${block}_mon = ${block}_monitor::type_id::create(\"${block}_mon\", this);"  >> ../../tb/${block}_agent.sv
	@echo "   endfunction // build_phase" >> ../../tb/${block}_agent.sv
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "   virtual function void connect_phase(uvm_phase phase);" >> ../../tb/${block}_agent.sv
	@echo "      super.connect_phase(phase);" >> ../../tb/${block}_agent.sv
	@echo "      ${block}_mon.${block}_mon_port.connect(${block}_agt_port); // mon -> refmod/coverage" >> ../../tb/${block}_agent.sv
	@echo "      ${block}_mon.ref_mon_port.connect(ref_agt_port); // mon -> comparator" >> ../../tb/${block}_agent.sv
	#-------------------------Alterar para mais transactions-------------------------------------
	
	
	#--------------------------------------------------------------------------------------------
	@echo "      ${block}_drv.seq_item_port.connect(${block}_sqr.seq_item_export); // sqr -> drv" >> ../../tb/${block}_agent.sv
	@echo "   endfunction // connect_phase" >> ../../tb/${block}_agent.sv
	@echo " " >> ../../tb/${block}_agent.sv
	@echo "endclass // ${block}_agent" >> ../../tb/${block}_agent.sv	