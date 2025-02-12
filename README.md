## Dataset Overview
- **File**: `Udemy data.csv`
- **Rows**: 3682
- **Columns**: 11
  - `course_id`, `course_title`, `is_paid`, `price`, `num_subscribers`, `num_reviews`, `num_lectures`, `level`, `content_duration`, `published_timestamp`, `subject`

## Key Questions Analyzed
1. **Subjects Offered**:  
   Udemy offers courses in 4 subjects:  
   `Musical Instruments`, `Business Finance`, `Graphic Design`, and `Web Development`.

2. **Most Popular Subject**:  
   `Web Development` has the highest number of courses (1200), followed by `Business Finance` (1199).

3. **Free vs. Paid Courses**:  
   - **Free Courses**: 310 courses (filtered using `df[df.is_paid == False]`).  
   - **Paid Courses**: 3372 courses (filtered using `df[df.is_paid == True]`).

4. **Top Selling Courses**:  
   Sorted by `num_subscribers` in descending order. The top course is *"Learn HTML5 Programming From Scratch"* with 268,923 subscribers.

5. **Graphic Design Courses Under $100**:  
   Filtered using `df[(df.subject == 'Graphic Design') & (df.price == '100')]` (note: the dataset uses string values for price, so exact numeric filtering may require data cleaning).

6. **Python-Related Courses**:  
   Filtered using `df[df.course_title.str.contains('Python')]`, revealing 28 courses in `Web Development` and `Business Finance`.

7. **Courses Published in 2015**:  
   Extracted by converting `published_timestamp` to datetime and filtering by year.

8. **Max Subscribers by Course Level**:  
   Grouped using `df.groupby('level')['num_subscribers'].max()`, showing `All Levels` courses have the highest subscribers (268,923).

## Usage
1. **Dependencies**:  
   Ensure `pandas` is installed:
   ```bash
   pip install pandas
