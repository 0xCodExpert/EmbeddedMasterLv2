PWD = $(shell pwd)
SRC = $(PWD)/src
INC = $(PWD)/include/symbol

MAIN = $(SRC)/main

LIBS = -lGL -lglut -lGLU -lgsl -lm

SRCS = $(wildcard *.c)
TARGET = $(SRCS:%.c=%)

DRAW_RESISTANCE = $(MAIN)/draw_resistance
DRAW_TRACE = $(MAIN)/draw_trace
DRAW_TEXT = $(MAIN)/draw_text
MOUSE_CLICK_COORD = $(MAIN)/mouse_click_coord
TRANSLATE_OBJECT = $(MAIN)/translate_object
DRAG_DROP_OBJECT = $(MAIN)/drag_drop_object
RL_CIRCUIT_SIM = $(MAIN)/rl_circuit_simulation
DRAW_CIRCUIT_SYMBOL = $(MAIN)/draw_circuit_symbol

#LINEAR_ALGEBRA = $(SRC)/linear_algebra
#SUBDIRS = $(LINEAR_ALGEBRA)

DRAW_CIRCUIT_SYM = $(SRC)/symbol
SUBDIRS = $(DRAW_CIRCUIT_SYM)

all: main
	@echo $(TARGET)
	$(shell rm -rf build)
	$(shell mkdir build)
	$(shell cp $(DRAW_RESISTANCE) ./build/)
	$(shell cp $(DRAW_TRACE) ./build/)
	$(shell cp $(DRAW_TEXT) ./build/)
	$(shell cp $(MOUSE_CLICK_COORD) ./build/)
	$(shell cp $(TRANSLATE_OBJECT) ./build/)
	$(shell cp $(DRAG_DROP_OBJECT) ./build/)
	$(shell cp $(RL_CIRCUIT_SIM) ./build/)
	$(shell cp $(DRAW_CIRCUIT_SYMBOL) ./build/)

main:	_all
	$(MAKE) -C $(MAIN)

_all:
	for dir in $(SUBDIRS); do \
		$(MAKE) -C $$dir; \
	done

clean:  mclear
	$(shell rm -rf build)

mclear:	_clean
	$(MAKE) -C $(MAIN) clean

_clean:
	for dir in $(SUBDIRS); do \
		$(MAKE) -C $$dir clean; \
	done
