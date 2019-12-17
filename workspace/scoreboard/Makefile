bloco1 = xxx
#bloco2 = xxx

scoreboard:
	@echo "class scoreboard extends uvm_scoreboard;" >> ../../tb/scoreboard.sv
	@echo "    \`uvm_component_utils(scoreboard)" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	@echo "    typedef uvm_in_order_class_comparator #(ref_transaction) comp_type;" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	@echo "    refmod rfm;" >> ../../tb/scoreboard.sv
	@echo "    comp_type comp;" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	#----------------------------------Alterar de acordo com as transactions---------------------------
	#exemplo @echo "    uvm_analysis_port #(${bloco1}_transaction) ${bloco1}_mon_port;" >> ../../tb/scoreboard.sv
	#exemplo @echo "    uvm_analysis_port #(${bloco2}_transaction) ${bloco2}_mon_port;" >> ../../tb/scoreboard.sv
	

	#--------------------------------------------------------------------------------------------------
	@echo "    uvm_analysis_port #(ref_transaction) ref_mon_port;" >> ../../tb/scoreboard.sv
	@echo "    uvm_analysis_port #(ref_transaction) ${bloco1}_ref_port;" >> ../../tb/scoreboard.sv
	@echo "    uvm_analysis_port #(ref_transaction) rfm_ref_port;" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	@echo "//Construtor" >> ../../tb/scoreboard.sv
	@echo "    function new(string name = \"scoreboard\", uvm_component parent);" >> ../../tb/scoreboard.sv
	@echo "       super.new(name, parent);" >> ../../tb/scoreboard.sv
	#----------------------------------Alterar de acordo com as portas criadas-------------------------
	#exemplo @echo "       ${bloco1}_mon_port = new(\"${bloco1}_mon_port\", this);" >> ../../tb/scoreboard.sv
	#exemplo @echo "       ${bloco1}_ref_port = new(\"${bloco1}_ref_port\", this);" >> ../../tb/scoreboard.sv


	#--------------------------------------------------------------------------------------------------
	@echo "       ref_mon_port = new(\"ref_mon_port\", this);" >> ../../tb/scoreboard.sv
	@echo "       rfm_ref_port = new(\"rfm_ref_port\", this);" >> ../../tb/scoreboard.sv 
	@echo "    endfunction // new" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	@echo "    virtual function void build_phase(uvm_phase phase);" >> ../../tb/scoreboard.sv
	@echo "        super.build_phase(phase);" >> ../../tb/scoreboard.sv
	@echo "        rfm = refmod::type_id::create(\"rfm\", this);" >> ../../tb/scoreboard.sv
	@echo "        comp = comp_type::type_id::create(\"comp\", this);" >> ../../tb/scoreboard.sv
	@echo "    endfunction // build_phase" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	@echo "    virtual function void connect_phase(uvm_phase phase);" >> ../../tb/scoreboard.sv
	@echo "       super.connect_phase(phase);" >> ../../tb/scoreboard.sv
	#-----------------------------------Alterar de acordo com as portas criadas------------------------
	#exemplo @echo "       alu_mon_port.connect(rfm.alu_pin); // alu_mon -> rfm" >> ../../tb/scoreboard.sv

		
	#--------------------------------------------------------------------------------------------------
	@echo "       ref_mon_port.connect(rfm.ref_pout); // ${bloco1}_ref -> rfm" >> ../../tb/scoreboard.sv
	@echo "       ${bloco1}_ref_port.connect(comp.before_export); // ${bloco1}_mon -> comp" >> ../../tb/scoreboard.sv
	@echo "       rfm.ref_pout.connect(comp.after_export); // rfm -> comp" >> ../../tb/scoreboard.sv
	@echo "    endfunction // connect_phase" >> ../../tb/scoreboard.sv
	@echo " " >> ../../tb/scoreboard.sv
	@echo "endclass // scoreboard" >> ../../tb/scoreboard.sv

refmod:
	#--------------------------------Colocar na linha abaixo a função que será o ref mod------------
	@echo "import \"DPI-C\" context function #preencher aqui#;" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	#----------------------Se você deseja que cada exportação chame um método write ()--------------
	#exemplo @echo " \`uvm_analysis_imp_decl(_alu)" >> ../../tb/refmod.sv
	#        @echo " \`uvm_analysis_imp_decl(_reg)" >> ../../tb/refmod.sv
	
	#-----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/refmod.sv
	@echo "class refmod extends uvm_component;" >> ../../tb/refmod.sv
	@echo "   \`uvm_component_utils(refmod)" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	#---------------------------------Alterar para a instanciação de transactions-------------------
	#exemplo @echo "    alu_transaction alu_tr_in;" >> ../../tb/refmod.sv
	
	#-----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/refmod.sv
	#---------------------------Receber transactions transmitidas por uvm_analysis_port-------------
	#exemplo uvm_analysis_imp #(transaction_in, refmod) in;
	#exemplo para mais de uma exportação chamando um método write()
	#@echo "    uvm_analysis_imp_alu #(alu_transaction, refmod) alu_pin;" >> ../../tb/refmod.sv
	#@echo "    uvm_analysis_imp_reg #(reg_transaction, refmod) reg_pin;" >> ../../tb/refmod.sv
	
	
	#-----------------------------------------------------------------------------------------------
	@echo "    uvm_analysis_port #(ref_transaction) ref_pout;" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	#--------------------------------------Definição de eventos-------------------------------------
	#exemplo @echo "    event begin_refmodtask, begin_regsupdate;" >> ../../tb/refmod.sv
	

	#-----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/refmod.sv
	#--------------------------------------Variáveis do refmod--------------------------------------
	#exemplo @echo "    logic [15:0] ref_regs [4];" >> ../../tb/refmod.sv
	

	#-----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/refmod.sv	
	@echo "    function new(string name = \"refmod\", uvm_component parent);" >> ../../tb/refmod.sv
	@echo "       super.new(name, parent);" >> ../../tb/refmod.sv
	#------------------definição das portas de entrada e saida e valores de inicio para reg---------
	#exemplos
	#@echo "       alu_pin = new(\"alu_pin\", this);" >> ../../tb/refmod.sv 
	#@echo "       ref_pout = new(\"ref_pout\", this);" >> ../../tb/refmod.sv
	#@echo "       ref_regs = {16'hC4F3, 16'hB45E, 16'hD1E5, 16'h1DE4};" >> ../../tb/refmod.sv
	

	#-----------------------------------------------------------------------------------------------
	@echo "       ref_pout = new(\"ref_pout\", this);" >> ../../tb/refmod.sv
	@echo "    endfunction // new" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	@echo "    virtual function void build_phase(uvm_phase phase);" >> ../../tb/refmod.sv
	@echo "       super.build_phase(phase);" >> ../../tb/refmod.sv
	@echo "    endfunction // build_phase" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	@echo "    virtual task run_phase(uvm_phase phase);" >> ../../tb/refmod.sv
	@echo "       super.run_phase(phase);" >> ../../tb/refmod.sv
	@echo "       fork" >> ../../tb/refmod.sv
	@echo "          refmod_task();" >> ../../tb/refmod.sv
	#----------------------------Alterar caso tenha mais task---------------------------------------
	
	
	#-----------------------------------------------------------------------------------------------
	@echo "          record_tr();" >> ../../tb/refmod.sv
	@echo "       join" >> ../../tb/refmod.sv
	@echo "    endtask // run_phase" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	@echo "    task refmod_task();" >> ../../tb/refmod.sv
	@echo "       forever begin" >> ../../tb/refmod.sv
	@echo "          @begin_refmodtask;" >> ../../tb/refmod.sv
	@echo "          ref_tr_out = ref_transaction::type_id::create(\"ref_tr_out\", this);" >> ../../tb/refmod.sv 
	@echo "          -> begin_record;" >> ../../tb/refmod.sv
	#--------------------------------Colocar na linha abaixo a função que será o ref mod------------
	@echo "          ref_tr_out.data_out = #preencher aqui;" >> ../../tb/refmod.sv
	#-----------------------------------------------------------------------------------------------
	@echo "          #10;" >> ../../tb/refmod.sv
	@echo "          -> end_record;" >> ../../tb/refmod.sv
	@echo "          ref_pout.write(ref_tr_out);" >> ../../tb/refmod.sv
	#--------------------------------Colocar na linha abaixo handshake-----------------------------
	#exemplo @echo "          wait(alu_tr_in.valid_out);"	>> ../../tb/refmod.sv 
	

	#----------------------------------------------------------------------------------------------  
	@echo "          end" >> ../../tb/refmod.sv
	@echo "    endtask // refmod_task" >> ../../tb/refmod.sv
	@echo " " >> ../../tb/refmod.sv
	#--------------------------------Local para se criar novas tasks-------------------------------
	

	#----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/refmod.sv
	#---------------------------------Task de escrita----------------------------------------------
	#exemplo
	# @echo "virtual function write (transaction_in t);" >> ../../tb/refmod.sv
	# @echo "    tr_in = transaction_in#()::type_id::create("tr_in", this);" >> ../../tb/refmod.sv
	# @echo "    tr_in.copy(t);" >> ../../tb/refmod.sv
	# @echo "-> begin_refmodtask;" >> ../../tb/refmod.sv
	# @echo "endfunction" >> ../../tb/refmod.sv

	
	#----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/refmod.sv
	@echo "   virtual task record_tr();" >> ../../tb/refmod.sv
	@echo "      forever begin" >> ../../tb/refmod.sv
	@echo "         @begin_record;" >> ../../tb/refmod.sv
	@echo "         begin_tr(ref_tr_out, \"refmod\");" >> ../../tb/refmod.sv
	@echo "         @end_record;" >> ../../tb/refmod.sv
	@echo "         end_tr(ref_tr_out);" >> ../../tb/refmod.sv
	@echo "      end" >> ../../tb/refmod.sv
	@echo "   endtask // record_tr" >> ../../tb/refmod.sv	 
	@echo " " >> ../../tb/refmod.sv
	@echo "endclass // refmod" >> ../../tb/refmod.sv


ref_transaction:
	@echo "class ref_transaction extends uvm_sequence_item;" >> ../../tb/ref_transaction.sv
	@echo " " >> ../../tb/ref_transaction.sv
	#--------------------------------------definir aqui os sinais de saida do refmod---------------
	

	#----------------------------------------------------------------------------------------------
	@echo " " >> ../../tb/ref_transaction.sv	
	@echo "function new (string name = \"ref_transaction\");" >> ../../tb/ref_transaction.sv
	@echo "super.new(name);" >> ../../tb/ref_transaction.sv
	@echo "endfunction // new" >> ../../tb/ref_transaction.sv
	@echo " " >> ../../tb/ref_transaction.sv
	@echo "\`uvm_object_param_utils_begin(ref_transaction)" >> ../../tb/ref_transaction.sv
	#--------------------------------------alterar aqui-------------------------------------------- 
	#exemplo @echo "\`uvm_field_int(data_out, UVM_UNSIGNED)" >> ../../tb/ref_transaction.sv
	#----------------------------------------------------------------------------------------------
	@echo "\`uvm_object_utils_end" >> ../../tb/ref_transaction.sv
	@echo " " >> ../../tb/ref_transaction.sv
	@echo "endclass // ref_transaction"	>> ../../tb/ref_transaction.sv	