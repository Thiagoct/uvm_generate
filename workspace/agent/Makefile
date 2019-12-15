block = alu

transaction:
	@echo "class ${block}_transaction extends uvm_sequence_item;" >> ../../tb/${block}_transaction.sv
	@echo "//Entradas do DUT" >> ../../tb/${block}_transaction.sv
	
	#---------------------------Alterar com as entradas do DUT--------------------------
	#exemplo @echo "rand bit [15:0] sinal;" >> ../../tb/${block}_transaction#
	
	@echo "rand bit [15:0] data_in;" >> ../../tb/${block}_transaction.sv
	@echo "rand bit [1:0] reg_sel;"	 >> ../../tb/${block}_transaction.sv
	@echo "rand bit [1:0]  instr;"   >> ../../tb/${block}_transaction.sv
	
	#-----------------------------------------------------------------------------------
	
	@echo "//Saídas do DUT" >> ../../tb/${block}_transaction.sv	
	
	#---------------------------Alterar com as saídas do DUT----------------------------
	#exemplo @echo "bit [15:0] sinal;" >> ../../tb/${block}_transaction#
	
	@echo "bit [31:0] data_out;" >> ../../tb/${block}_transaction.sv	

	#-----------------------------------------------------------------------------------	
	
	@echo "//Construtor" >> ../../tb/${block}_transaction.sv
	@echo "function new (string name = \"${block}_transaction\");" >> ../../tb/${block}_transaction.sv
	@echo "	  super.new(name);" >> ../../tb/${block}_transaction.sv
	@echo "endfunction // new" >> ../../tb/${block}_transaction.sv	

	@echo "// Macros" >> ../../tb/${block}_transaction.sv
	@echo "\`uvm_object_param_utils_begin(alu_transaction)" >> ../../tb/${block}_transaction.sv
	@echo "   \`uvm_field_int(data_in, UVM_UNSIGNED)" >> ../../tb/${block}_transaction.sv
	@echo "   \`uvm_field_int(reg_sel, UVM_UNSIGNED)" >> ../../tb/${block}_transaction.sv
	@echo "   \`uvm_field_int(instr, UVM_UNSIGNED)" >> ../../tb/${block}_transaction.sv
	@echo "   \`uvm_field_int(valid_in, UVM_BIN)" >> ../../tb/${block}_transaction.sv
	@echo "   \`uvm_field_int(data_out, UVM_UNSIGNED)" >> ../../tb/${block}_transaction.sv
	@echo "   \`uvm_field_int(valid_out, UVM_BIN)" >> ../../tb/${block}_transaction.sv
	@echo "\`uvm_object_utils_end" >> ../../tb/${block}_transaction.sv

	@echo "endclass // ${block}_transaction" >> ../../tb/${block}_transaction.sv
