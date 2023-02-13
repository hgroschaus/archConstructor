##
## EPITECH PROJECT, 2023
## Makefile
## File description:
## Makefile
##

NAME	=	exe

CC	=	g++

DIR	=	src/

DIR_TEST	=	tests/

DIR_INC = include/

SRC	=	main.cpp

SRC_PATHS	=	$(addprefix $(DIR), $(SRC))

SRC_TEST	=	$(DIR_TEST)unit_tests.cpp

OBJ	=	$(SRC_PATHS:.cpp=.o)

INCLUDE	=	-I$(DIR_INC)

CPPFLAGS	=	-std=c++20 -Wall -Wextra -Werror $(INCLUDE)

LDFLAGS_TEST = --coverage -lcriterion

LDFLAGS	=

NAME_TEST	=	unit_tests

.PHONY:	re fclean clean all debug

all:	$(NAME)

clean:
	$(RM) -f $(OBJ)

fclean:	clean
	$(RM) $(NAME)
	$(RM) $(NAME_TEST)
	$(RM) *.gc*

re:	fclean all

debug:	CFLAGS += -g3

debug:	all

$(NAME):	$(OBJ)
	$(CC) -o $(NAME) $(OBJ) $(CPPFLAGS) $(LDFLAGS)

tests_run:
	$(CC) -o $(NAME_TEST) $(SRC_PATHS) $(SRC_TEST) $(CPPFLAGS) $(LDFLAGS_TEST)
	$(RM) *.gc*
	./$(NAME_TEST)
	$(RM) *.gc*
