# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: jinbkim <jinbkim@student.42.fr>            +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2020/07/26 18:29:02 by jinbkim           #+#    #+#              #
#    Updated: 2020/09/09 12:33:04 by jinbkim          ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME	= minishell
LIB		= libft
MINI	= src
OBJ		= *.o
RM		= rm -rf
CC		= gcc
CFLAGS	= -Wall -Wextra -Werror -g -fsanitize=address

all 	: $(NAME)

clean	:
		$(RM) $(OBJS) *.gch *.out
		make clean -C $(LIB)
		make clean -C $(MINI)

fclean	: clean
		$(RM) $(NAME)
		make fclean -C $(LIB)
		make fclean -C $(MINI)

re		: fclean all

$(NAME) :
		make -C $(LIB)
		make -C $(MINI)
		$(CC) -o minishell $(CFLAGS) $(LIB)/$(OBJ) $(MINI)/$(OBJ)