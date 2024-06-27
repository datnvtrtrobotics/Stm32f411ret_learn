# Stm32f411ret_learn


This repository contains a Makefile for building an embedded project targeting the stm32f411ret6 microcontroller


Compiler and tools
CC: Trình biên dịch C cho vi điều khiển ARM Cortex-M4.
AS: Trình biên dịch assembler.
CP: Lệnh sao chép đối tượng từ tệp ELF sang các định dạng khác.
SZ: Công cụ đo kích thước của các phần trong tệp ELF.


Project name và Directories
TARGET: tên dự án.
SRCDIR, INCDIR, STARTUP_DIR, DRVDIR: Các thư mục chứa mã nguồn, tập tin header, startup code và các driver.


Source files và Object files
SRCS: Danh sách các tệp nguồn (.c và .s) được tự động xác định bằng lệnh wildcard.
OBJS: Danh sách các tệp object (.o) tương ứng với các tệp nguồn.


Includes và Compiler flags
INCLUDES: Các thư mục chứa các file header cần thiết.
CFLAGS: Các cờ biên dịch bao gồm kiến trúc vi điều khiển, tiêu chuẩn ngôn ngữ, các cờ tối ưu hóa, và các định nghĩa (#define) cần thiết.


Linker script và Linker flags
LDSCRIPT: Tệp script liên kết (linker script) được sử dụng để chỉ định cấu trúc bộ nhớ của vi điều khiển.
LDFLAGS: Các cờ liên kết bao gồm tệp script liên kết, cấu hình giảm thiểu kích thước, tạo tệp map để phân tích mã nguồn.


Rules
all: Mục tiêu chính là tạo ra file nhị phân (.bin).
$(TARGET).elf: Quy tắc để tạo file thực thi ELF từ các file object.
%.o: Quy tắc để biên dịch các file nguồn (.c và .s) thành các file object.
$(TARGET).bin: Quy tắc để sao chép file nhị phân từ file ELF.


clean: Mục tiêu để xóa các file object và các file thực thi đã tạo ra.
flash: Mục tiêu để ghi file nhị phân lên vi điều khiển sử dụng st-flash.
.PHONY: Định nghĩa các mục tiêu không phụ thuộc vào tên file, mà chỉ thực hiện các hành động nào đó.
