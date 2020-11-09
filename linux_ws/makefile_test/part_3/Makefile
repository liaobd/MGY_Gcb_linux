#make变量以及四种赋值方式的示例，请在终端输出并思考
VAR_A=FILEA
VAR_B=$(VAR_A)
VAR_C:=$(VAR_A)
VAR_A+=FILEB
VAR_D?=FILED
.PHONY:check
check:
	@echo "var_a:"$(VAR_A)
	@echo "var_b:"$(VAR_B)
	@echo "var_c:"$(VAR_C)
	@echo "var_d:"$(VAR_D)


