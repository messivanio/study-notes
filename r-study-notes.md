R Study Notes
=============

```R

    5 ^ 14 # Exponentiation
    5 %% 3 # Modulo

    my_decimal <- 5.3
    my_integer <- 3
    my_logical <- TRUE
    my_characters <- "abc"

    class(my_numeric) # Returns "numeric"

```

## Vectors

```R

    # Vectors ... c()
    numeric_vector <- c(44, 20, 12)
    character_vector <- c("a", "b", "c", "d", "e")

    # Naming the vector elements
    names(numeric_vector) <- c("first", "last", "middle")

    # Sum two vectors (element-wise sum)
    the_vector <- c(1, 2, 3)
    another_vector <- c(4, 5, 6)
    the_vector + another_vector # returns 5 7 9

    # Sum and mean of element vectors
    sum(the_vector) # returns 6
    mean(the_vector) # average of the vector elements


    # First vector element
    the_vector[1] # First element has index 1
    
    # Picking vector elements
    character_vector[c(2, 4, 5)] # returns b d e
    character_vector[2:4] # returns b c d
    numeric_vector("first") # returns 44
    numeric_vector(c("last", "middle")) # returns 20 12

    # Selection by comparation
    numeric_vector > 15  # returns TRUE TRUE FALSE
    numeric_vector == 20  # returns FALSE TRUE FALSE
    numeric_vector != 20  # returns TRUE FALSE TRUE
    numeric_vector[numeric_vector != 20]  # returns 44 12

```

## Matrices

```R

    my_matrix <- matrix(1:7, byrow=TRUE, nrow=3)
    # byrow = TRUE -> filled by rows
    # byrow = FALSE -> filled by columns

    colnames(my_matrix) <- col_names_vector
    rownames(my_matrix) <- row_names_vector

    rowSums(my_matrix)
    colSums(my_matrix)

    cbind(a_matrix, another_matrix, a_vector)  #  merges matrices and/or vectors together by column
    rbind(a_matrix, another_matrix, a_vector)  #  merges matrices and/or vectors together by row

    a_matrix[1,2]
    a_matrix[1:3,2:3]
    a_matrix[3,] # Row 3 / all columns
    a_matrix[,2] # Column 2 / all rows

    a_matrix * 8  # element-wise multiplication
    a_matrix * another_matrix  # non-traditional matrix multiplication

```

## Factors

Categorical Variables

```R

    color_vector <- c("Red", "Blue", "Blue", "Green", "Red")
    factor_color_vector <- factor(color_vector)
    
    factor_temperature_vector <- factor(temperature_vector, order = TRUE, levels = c("Low", "Medium", "High"))
    # same as
    levels(factor_temperature_vector) <- c("Low", "Medium", "High")

```



# References

[Introduction to R - Jonathan Cornelissen - DataCamp](https://www.datacamp.com/courses/free-introduction-to-r)
