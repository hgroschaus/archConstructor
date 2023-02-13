##
## EPITECH PROJECT, 2023
## Makefile
## File description:
## Makefile
##

NAME	=	exe

CC	=	gcc

DIR	=	src/

DIR_TEST	=	tests/

DIR_INC	=	include/

SRC	=	$(DIR)main.c

SRC_TEST	=	$(DIR_TEST)unit_tests.c

OBJ	=	$(SRC:.c=.o)

CPPFLAGS	=	-std=gnu17 -Wall -Wextra -Werror -I$(DIR_INC)

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
	$(CC) -o $(NAME_TEST) $(SRC) $(SRC_TEST) $(CPPFLAGS) $(LDFLAGS_TEST)
	$(RM) *.gc*
	./$(NAME_TEST)
	$(RM) *.gc*
