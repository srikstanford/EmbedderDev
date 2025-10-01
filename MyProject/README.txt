<COMMANDS>
# --- Build / Compile --------------------------------------------------------
build_command = make -C Debug -j16 all

# --- Flash ------------------------------------------------------------------
# Example using st-flash (adjust address for your MCU)
flash_command = STM32_Programmer_CLI -c port=SWD freq=4000 -w Debug/program.elf

# --- Debug ------------------------------------------------------------------
# ST-Link will expose a GDB server on port 61234 by default
gdb_server_command = ST-LINK_gdbserver -d -v -t -cp /opt/st/stm32cubeclt_1.18.0/STM32CubeProgrammer/bin
gdb_server_host = localhost
gdb_server_port = 61234
gdb_client_command = arm-none-eabi-gdb
target_connection = remote

# --- Serial Monitor ----------------------------------------------------------
serial_port = /dev/ttyACM0
serial_baudrate = 115200
serial_monitor_command = tio {port} -b {baud}
serial_monitor_interactive = false