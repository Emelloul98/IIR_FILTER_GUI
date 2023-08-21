# runs on pycharm only !!
import matplotlib.pyplot as plt
import matplotlib.patches as patches


def fir_filter_diagram(coefficients):
    plt.figure(figsize=(16, 6))
    block_width = 0.45
    spacing = 0.5
    middle_spacing = 1.5
    start_x = 2
    # Draw the plus sign block below the existing blocks:
    plus_block_width = 0.4
    plus_block_x = start_x + (len(coefficients) - 1) * (block_width + spacing) / 2
    last_block = 0
    for i in range(len(coefficients) - 1):
        last_block = block_x = start_x + i * (block_width + spacing)
        rectangle = patches.Rectangle((block_x, 2), block_width, 1, fill=True, color='blue')
        plt.gca().add_patch(rectangle)
        plt.text(block_x + block_width / 2, 2.5, r'$z^{-1}$', color='black', va='center', ha='center', fontsize=10)
        for j in range(len(coefficients) - 1):
            plt.annotate('', xy=(start_x + j * (block_width + spacing) + block_width, 2.625),
                         xytext=(start_x + (j + 1) * (block_width + spacing), 2.625),
                         arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
            # Draw circles below each arrow
            circle_x = (start_x - spacing / 2) + j * (block_width + spacing)
            circle = patches.Circle((circle_x, 1.4), 0.2, fill=False, color='blue', linewidth=2)
            plt.gca().add_patch(circle)
            # Add 'X' sign in the middle of each circle
            plt.text(circle_x, 1.4, 'X', color='black', va='center', ha='center', fontsize=12)
            # Draw arrows from each arrow to each circle
            plt.annotate('', xy=(start_x + j * (block_width + spacing) - spacing / 2, 2.625),
                         xytext=(circle_x, 1.6),
                         arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
            # Draw arrows from each circle to the plus sign block
            plt.annotate('', xy=(circle_x, 1.2), xytext=(plus_block_x + plus_block_width / 2, 0.2),
                         arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
            # Move the coefficient numbers to the left of each circle
            plt.text(block_x - 0.25 - spacing, 1.4, coefficients[i], color='black',
                     va='center', ha='center', fontsize=10)
    # Draw additional circles at the end of the line
    end_circle_x = (start_x - spacing / 2) + (len(coefficients) - 1) * (block_width + spacing)
    end_circle = patches.Circle((end_circle_x, 1.4), 0.2, fill=False, color='blue', linewidth=2)
    plt.gca().add_patch(end_circle)
    plt.text(end_circle_x, 1.4, 'X', color='black', va='center', ha='center', fontsize=12)
    plt.annotate('', xy=(end_circle_x, 2.625), xytext=(end_circle_x, 1.6),
                 arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
    plt.annotate('', xy=(end_circle_x, 1.2), xytext=(plus_block_x + plus_block_width / 2, 0.2),
                 arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
    plt.text(last_block + spacing - 0.25, 1.4, coefficients[len(coefficients) - 1],
             color='black', va='center', ha='center', fontsize=10)
    # Draw arrow and label for x(n):
    plt.annotate('', xy=(start_x - middle_spacing / 2, 2.625), xytext=(start_x, 2.625),
                 arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
    plt.text(start_x - middle_spacing / 1.5, 2.6, r'$x(n)$', color='black', va='center', ha='center', fontsize=15)
    # plus sign block::
    rectangle_plus = patches.Rectangle((plus_block_x, -0.25), plus_block_width, plus_block_width, fill=True,
                                       color='blue')
    plt.gca().add_patch(rectangle_plus)
    plt.text(plus_block_x + plus_block_width / 2, -0.1, "\u03A3", color='black', va='center', ha='center', fontsize=20)
    # Draw a short line and label under the plus sign block:
    plt.text(plus_block_x + plus_block_width / 2, -0.9, r'$y(n)$', color='k', va='bottom', ha='center', fontsize=15)
    # Draw a line connecting y(n) to the plus sign block with an arrow
    plt.annotate('', xy=(plus_block_x + plus_block_width / 2, -0.6), xytext=(plus_block_x + plus_block_width / 2, -0.2),
                 arrowprops=dict(arrowstyle='->', color='black'))
    plt.title('FIR Filter')
    plt.xticks([i for i in range(17)], ['', '0', '', '1', '', '2', '', '3', '', '4', '', '5', '', '6', '', '7', ''])
    plt.gca().set_xlim(0, 20)
    plt.gca().set_ylim(-1, 3)
    plt.gca().set_xticklabels(plt.gca().get_xticklabels(), fontsize=8)
    plt.gca().set_yticklabels([])
    plt.show()


def iir_filter_diagram(coefficients1, coefficients2):
    plt.figure(figsize=(16, 6))
    num_of_blocks1 = len(coefficients1) - 1
    num_of_blocks2 = len(coefficients2) - 1
    spacing = 0.15
    block_width = 0.4
    circles_size1 = 0.15
    circles_size2 = 0.15
    if num_of_blocks1 > 6:
        block_height1 = (3 - (spacing * (num_of_blocks1 - 1))) / num_of_blocks1
        circles_size1 = 0.1
    else:
        block_height1 = 0.4
    middle_spacing = 1.5
    start_x1 = 2
    start_x2 = 13
    start_y1 = 2.3
    start_y2 = 2.2

    block_start = start_y1 - middle_spacing / 2 + 0.1
    # Draw arrow and label for x(n):
    plt.annotate('', xy=(block_start, 2.6), xytext=(start_x1, 2.6),
                 arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
    plt.text(start_x1 - middle_spacing / 1.5, 2.6, r'$x(n)$', color='black', va='center', ha='center', fontsize=15)
    # Draw plus block:
    rectangle_plus = patches.Rectangle((8.0, 2.6), 0.5, 0.2, fill=True, color='blue')
    plt.gca().add_patch(rectangle_plus)
    plt.text(8.25, 2.7, "\u03A3", color='black', va='center', ha='center', fontsize=15)
    # Draw y(n):
    plt.text(17, 2.7, r'$y(n)$', color='k', va='bottom', ha='center', fontsize=15)
    # Draw a line to y(n):
    plt.annotate('', xy=(8.5, 2.8), xytext=(16.5, 2.8), arrowprops=dict(arrowstyle='<-', color='black'))
    for i in range(len(coefficients1)):
        block_y = start_y1 - i * (block_height1 + spacing)
        if i != len(coefficients1) - 1:
            # block design:
            rectangle = patches.Rectangle((start_x1, block_y), block_width, block_height1, fill=True, color='blue')
            plt.gca().add_patch(rectangle)
            # z^-1 design:
            plt.text(start_x1 + block_width / 2, block_y + block_height1 / 2, r'$z^{-1}$', color='black', va='center',
                     ha='center', fontsize=10)
        # Draw arrows between blocks design:
        arrow_start = block_y + block_height1
        arrow_end = arrow_start + spacing
        plt.annotate('', xy=(start_x1, arrow_start), xytext=(start_x1, arrow_end),
                     arrowprops=dict(arrowstyle='->', color='black', lw=1.5))
        # Draw circles below each arrow
        middle = (arrow_end + arrow_start) / 2
        circle_x = 2 * start_x1
        circle = patches.Circle((circle_x, middle), circles_size1, fill=False, color='blue', linewidth=2)
        plt.gca().add_patch(circle)
        # Draw 'X' inside each circle:
        plt.text(circle_x, middle, 'X', color='black', va='center', ha='center', fontsize=12)
        # Draw arrows form the block arrows to the circles:
        plt.annotate('', xy=(start_x1, middle), xytext=(circle_x - 0.1, middle),
                     arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
        # Draw the numbers of the array a:
        mid = (start_x1 + circle_x) / 2
        plt.text(mid, middle + 0.1, coefficients1[i], color='black', va='center', ha='center', fontsize=10)
        # Draw lines from the circles to the plus block:
        plt.annotate('', xy=(circle_x + 0.15, middle), xytext=(8, 2.65),
                     arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
    if num_of_blocks2 > 5:
        block_height2 = (3 - (spacing * (num_of_blocks2 - 1))) / num_of_blocks2
        circles_size2 = 0.1
    else:
        block_height2 = 0.4
        start_y2 = 2
    for j in range(len(coefficients2)):
        block_y = start_y2 - j * (block_height2 + spacing)
        if j != len(coefficients2) - 1:
            # block design:
            rectangle = patches.Rectangle((start_x2, block_y), block_width, block_height2, fill=True, color='blue')
            plt.gca().add_patch(rectangle)
            # z^-1 design:
            plt.text(start_x2 + block_width / 2, block_y + block_height2 / 2, r'$z^{-1}$', color='black', va='center',
                     ha='center', fontsize=10)
        # Draw arrows between blocks design:
        arrow_start = block_y + block_height2
        arrow_end = arrow_start + spacing
        plt.annotate('', xy=(start_x2, arrow_start), xytext=(start_x2, arrow_end),
                     arrowprops=dict(arrowstyle='->', color='black', lw=1.5))
        # Draw circles below each arrow
        middle = (arrow_end + arrow_start) / 2
        circle_x = 11
        circle = patches.Circle((circle_x, middle), circles_size2, fill=False, color='blue', linewidth=2)
        plt.gca().add_patch(circle)
        # Draw 'X' inside each circle:
        plt.text(circle_x, middle, 'X', color='black', va='center', ha='center', fontsize=12)
        # Draw arrows form the block arrows to the circles:
        plt.annotate('', xy=(start_x2, middle), xytext=(circle_x + 0.1, middle),
                     arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
        # Draw the numbers of the array b:
        mid = (start_x2 + circle_x) / 2
        plt.text(mid, middle + 0.1, coefficients2[j], color='black', va='center', ha='center', fontsize=10)
        # Draw lines from the circles to the plus block:
        plt.annotate('', xy=(circle_x - 0.15, middle), xytext=(8.5, 2.65),
                     arrowprops=dict(arrowstyle='<-', color='black', lw=1.5))
    plt.title('IIR Filter')
    plt.xticks([i for i in range(17)], ['', '0', '', '1', '', '2', '', '3', '', '4', '', '5', '', '6', '', '7', ''])
    plt.gca().set_xlim(0, 20)
    plt.gca().set_ylim(-1, 3)
    plt.gca().set_xticklabels(plt.gca().get_xticklabels(), fontsize=8)
    plt.gca().set_yticklabels([])
    plt.show()


# The Main:
a = input("enter the first array coefficients:")
b = input("enter the second array coefficients:")
# Split the input string into individual numbers
numbers1 = a.split()
numbers2 = b.split()
# Initialize an empty list to store the formatted coefficients
coefficient1 = []
coefficient2 = []
# Iterate through the numbers and format them as strings with one decimal place
for num1 in numbers1:
    coefficient1.append(f'{float(num1):.1f}')
for num2 in numbers2:
    coefficient2.append(f'{float(num2):.1f}')
if len(coefficient2) == 0:
    fir_filter_diagram(coefficient1)
else:
    iir_filter_diagram(coefficient1, coefficient2)

