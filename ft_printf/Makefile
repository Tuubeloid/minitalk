# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: tvalimak <tvalimak@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2023/11/18 19:09:58 by tvalimak          #+#    #+#              #
#    Updated: 2024/02/26 19:19:42 by tvalimak         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME		= libftprintf.a
INCLUDE		= include
LIBFT		= libft/
SRC_DIR		= src/
OBJ_DIR		= obj/
CC			= gcc
CFLAGS		= -Wall -Werror -Wextra -g -I 
RM			= rm -f
AR			= ar rcs

SRC_FILES	= ft_printf ft_printf_nbr ft_printf_hex


SRC			= $(addprefix $(SRC_DIR), $(addsuffix .c, $(SRC_FILES)))
OBJ			= $(addprefix $(OBJ_DIR), $(addsuffix .o, $(SRC_FILES)))

OBJF		= $(OBJ_DIR).cache_exists

all:		$(NAME)

$(NAME):	$(OBJ)
			make bonus -C $(LIBFT)
			cp libft/libft.a .
			mv libft.a $(NAME)
			$(AR) $(NAME) $(OBJ)

$(OBJ_DIR)%.o: $(SRC_DIR)%.c | $(OBJF)
			$(CC) $(CFLAGS) $(INCLUDE) -c $< -o $@

$(OBJF):
			mkdir -p $(OBJ_DIR)
			touch $(OBJF)

clean:
			$(RM) -r $(OBJ_DIR)
			make clean -C $(LIBFT)

fclean:		clean
			$(RM) $(NAME)
			$(RM) $(LIBFT)/libft.a

re:			fclean all

.PHONY:		all clean fclean re
