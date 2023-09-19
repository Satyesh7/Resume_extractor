# Resume_extractor
This Resume Extractor comprises a PDF extractor that extracts the details of the education section and skills section of the resume.
Then it compares the extracted details against the job description given and ranks them and shows the top 5 CVs for the job.

1. Extraction of Education and Skills Sections:
   - Challenge: The task required the extraction of specific sections, namely the "Education" and "Skills" sections, from the CVs. Detecting the start and end of these sections while ignoring other details was a challenge.
   - Solution: To address this challenge, custom functions were created to identify the start and end of the "Education" and "Skills" sections within the text. These functions iterated through the CV text and used specific keywords and headers as indicators to determine the boundaries of these sections.

2. Efficient Execution:
   - Challenge: The initial code execution was taking a considerable amount of time, especially when dealing with a large number of CVs and job descriptions.
   - Solution: The code was optimized by implementing parallel processing using the `multiprocessing` module. This improvement significantly reduced execution time by parallelizing the calculation of cosine similarity scores for each job description. The number of parallel processes was adjusted to optimize performance further.

3. Network Issues (Previous Issue):
   - Challenge: There were issues related to network timeouts during the loading of the DistilBERT model and tokenizer from Hugging Face's model hub.
   - Solution: To mitigate network issues, the code increased the timeout duration for requests. Additionally, the code was executed during periods of stable network connectivity.

4. Task Completion Point:
   - Challenge: The task required stopping the extraction process after successfully capturing the "Education" and "Skills" sections, ensuring that other irrelevant details were not extracted.
   - Solution: Custom functions were designed to recognize specific headers, such as "Education" and "Skills," as signals to stop extracting content for those sections. These functions used flags to control the extraction process, allowing the code to focus only on the required sections.

5. Custom Text Processing:
   - Challenge: Processing text data to tokenize and embed it efficiently while ensuring the code captures the semantic meaning was a critical task.
   - Solution: The code leveraged the DistilBERT model and tokenizer, which are pretrained on a vast amount of text data and are well-suited for this task. It used these tools to tokenize and embed the text data, capturing the contextual and semantic information necessary for cosine similarity calculations.

Addressing these challenges allowed for the successful implementation of the CV ranking and matching process, resulting in the identification of the top 5 candidates for each job description based on similarity scores.
