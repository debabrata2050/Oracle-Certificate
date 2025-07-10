# Oracle Exam 1Z0-184-25 : Oracle AI Vector Search Professional Dump

#### Q. Which statement best describes the core functionality and benefit of Retrieval Augmented Generation (RAG) in Oracle Database 23ai?
- [ ] It primarily aims to optimize the performance and efficiency of LLMs by using advanced data retrieval techniques, thus minimizing response times, and reducing computational overhead.
- [ ] It enables Large Language Models (LLMs) to access and process real-time data streams from diverse sources to generate the most up-to-date insights.
- [x] It empowers LLMs to interact with private enterprise data stored within the database, leading to more context-aware and precise responses to user queries. ✅
- [ ] It allows users to train their own specialized LLMs directly within the Oracle Database environment using their internal data, thereby reducing the reliance on external Al providers.

#### Q. What are the key advantages and considerations of using Retrieval Augmented Generation (RAG) in the context of Oracle Al Vector Search?
- [ ] It focuses on training specialized LLMs within the database environment for specific tasks, offering greater control over model behavior and data privacy but potentially requiring more development effort.
- [x] It leverages existing database security and access controls, thereby enabling secure and controlled access to both the database content and the LLM. ✅
- [ ] It excels at optimizing the performance and efficiency of LLM inference through advanced caching and precomputation techniques, leading to faster response times but potentially increasing storage requirements.
- [ ] It prioritizes real-time data extraction and summarization from various sources to ensure the LLM always has the most up-to-date information.

#### Q. When using SQL*Loader to load vector data for search applications, what is a critical consideration regarding the formatting of the vector data within the input CSV file?
- [ ] Use sparse format for vector data.
- [ ] Enclose vector components in curly braces ({).
- [x] As FVECis a binary format and the vector dimensions have a know width, fixed offsets can be used to make parsing the vectors fast and efficient. ✅
- [ ] Rely on SQL*Loader's automatic normalization of vector data.

#### Q. What is one type of notebook used for interacting with Select Al?
- [x] Oracle Machine Learning (OML) Notebooks ✅
- [ ] Wyde Rule Notebooks
- [ ] RoCE Notebooks

#### Q. How does an application use vector similarity search to retrieve relevant information from a database, and how is this information then integrated into the generation proce:
- [ ] Clusters similar text chunks and randomly selects one from the most relevant cluster.
- [ ] Trains a separate LLM on the database and uses it to answer, ignoring the general LLM.
- [x] Encodes the question and database chunks into vectors, finds the most similar using cosine similarity, and includes them in the LLM prompt. ✅
- [ ] Converts the question to keywords, searches for matches, and inserts the text into the response.

#### Q. What is the function of the COSINE parameter in the SQL query used to retrieve similar vectors?
```sql
topK = 3
sql = f"""select payload, vector _distance(vector, :vector, COSINE) as score from {table name} order by score fetch approx first
{topK} rows only"""
```
- [ ] It filters out vectors with a cosine similarity below a certain threshold.
- [ ] It specifies the type of vector encoding used in the database.
- [x] It indicates that the cosine distance metric should be used to measure similarity between vectors. ✅
- [ ] It converts the vectors to a format com patible with the SQL database.

#### Q. In the following Python code, what is the significance of prepending the source filename to each text chunk before storing it in the vector database?
```python
docs = [{'text': filename + ' | ' + section, 'path': filename} for filename, sections in faqs.items() for section in sections]
# Sample the resulting data
docs[:2]
```
- [ ] It speeds up the vectorization process by providing a unique identifier for each chunk.
- [ ] It improves the accuracy of the LLM by providing additional training data.
- [x] It preserves context and aids in the retrieval process by associating each vectorized chunk with its original source file. ✅
- [ ] It helps differentiate between chunks from different files but has no impact on vectorization.

#### Q. Which Python library is used to vectorize text chunks and the user's question in the following example?
```python
import oracledb

connection = oracledb.connect(user=un, password=pw, dsn=cs)
table_name = 'fags'

with connection.cursor() as cursor:
    # Create the table
    create_table_sql = f"""
    CREATE TABLE IF NOT EXISTS {table_name} (
    id NUMBER PRIMARY KEY,
    payload CLOB CHECK (payload IS JSON),
    vector VECTOR
    )"""
    try:
        cursor.execute(create_table_sql)
    except oracledb.DatabaseError as e:
        raise

connection.autocommit = True

from sentence_transformers import SentenceTransformer
encoder = SentenceTransformer("all-MiniLM-L12-v2")

```
- [ ] sentence_transformers
- [x] oracledb ✅
- [ ] oci
- [ ] json

#### Q. Which DDL operation is NOT permitted on a table containing a VECTOR column in Oracle Database 23ai?
- [ ] Adding a new VECTOR column to the table
- [ ] Dropping an existing VECTOR column from the table
- [x] Modifying the data type of an existing VECTOR column to a non-VECTOR type ✅
- [ ] Creating a new table using CTAS CREATE TABLE AS SELECT that includes the VECTOR column from the original table

#### Q. Which SQL statement correctly adds a VECTOR column named v with 4 dimensions and FLOAT32 format to an existing table named my_table?
- [ ] ALTER TABLE my_table MODIFY (v VECTOR(4, FLOAT32))
- [ ] UPDATE my_table SET v = VECTOR(4, FLOAT32)
- [x] ALTER TABLE my_table ADD v VECTOR(4, FLOAT32) ✅
- [ ] ALTER TABLE my_table ADD (v VECTOR(4, FLOAT32))

#### Q. Which statement best describes the capability of Oracle Data Pump for handling vector data in the context of vector search applications?
- [ ] Because of the complexity of vector data, Data Pump requires a specialized plug-in to handle the export and import operations involving vector data types.
- [x] Data Pump provides native support for exporting and importing tables containing vector data types, facilitating the transfer of vector data for vector search applications ✅
- [ ] Data Pump can only export and import vector data if the vector embeddings are stored as BLOB (Binary Large Object) data types in the database.
- [ ] Data Pump treats vector embeddings as regular text strings, which can lead to data corruption or loss of precision when transferring vector data for vector search.

#### Q. Which parameter is used to define the number of closest vector candidates considered during HNSW index creation?
- [ ] VECTOR _MEMORY SIZE
- [ ] NEIGHBORS
- [ ] TARGET ACCURACY
- [x] EFCONSTRUCTION ✅

#### Q. A retail company uses an Oracle Database 23ai HNSW vector index to recommend products to customers based on their browsing history.
The database administrator notices that the after restarting the database, product recommendations are slower.
What steps should the administrator take to resolve the issue?
- [ ] Decrease the VECTOR MEMORY SIZE parameter.
- [ ] Modify the distance metric to DOT.
- [x] Rebuild the HNSW index or enable automatic reload.
- [ ] Adjust the NEIGHBOR PARTITION PROBES parameter for improved accuracy.

#### Q. A database administrator wants to change the VECTOR_MEMORY_SIZE parameter for a pluggable database (PDB) in Oracle Database 23ai. Which SQL command is correct?
- [x] ALTER SYSTEM SET vector memory size=1G SCOPE=SGA; ✅
- [ ] ALTER DATABASE SET vector_memory_size=1G SCOPE=VECTOR;
- [ ] ALTER SYSTEM SET vector_memory_size=1G SCOPE=BOTH;
- [ ] ALTER SYSTEM RESET vector_memory_size;

#### Q. Which vector index available in Oracle Database 23ai is known for its speed and accuracy, making it a preferred choice for vector search?
- [ ] Inverted File System (IFS) index
- [ ] Full-Text (FT) index
- [ ] Binary Tree (BT) index
- [x] Hierarchical Navigable Small World (HNSW) index ✅

#### Q. If a query vector uses a different distance metric than the one used to create the index, what happens?
- [ ] The query fails.
- [ ] A warning is logged, but the query executes.
- [ ] The index automatically updates.
- [x] An exact match search is triggered. ✅

#### Q. What is the primary difference between the HNSW and IVF vector indexes in Oracle Database 23ai?
- [ ] HNSW guarantees accuracy, whereas IVF sacrifices performance for accuracy.
- [ ] HNSW is partition based, whereas IVF uses neighbor graphs for indexing.
- [x] HNSW uses an in-memory neighbor graph for faster approximate searches, whereas IVF use the buffer cache with partitions. ✅
- [ ] Both operate identically but differ in memory usage.

#### Q. What is a key advantage of generating vector embeddings outside the database?
- [ ] Reduced storage requirements
- [ ] Simplified data management
- [x] Flexibility in choosing specialized embedding models ✅
- [ ] Improved data security

#### Q. When generating vector embeddings for a new dataset outside of Oracle Database 23ai, which factor is crucial to ensure meaningful similarity search results?
- [ ] The physical location where the vector embeddings are stored
- [ ] The choice of programming language used to process the dataset (for example, Python, Java)
- [ ] The storage format of the new dataset (for example, CSV, JSON)
- [x] The same vector embedding model must be used for vectorizing the data and creating a query vector ✅

#### Q. When generating vector embeddings outside the database, what is the most suitable option for storing the embeddings for later use?
- [ ] In a binary FVEC file with the relational data in a CSV file
- [x] In a dedicated vector database ✅
- [ ] In a CSV file
- [ ] In the database as BLOB (Binary Large Object) data

#### Q. What does a target accuracy of 80% in an approximate similarity search imply?
- [ ] 80% accuracy seen in the index calculated distances.
- [ ] The search will process 80% of the dataset.
- [ ] 80% of the query results will match the exact search results.
- [x] Only 80% of the indexed vectors are used. ✅

#### Q. Which is a characteristic of an approximate similarity search in Oracle Database 23ai?
- [x] It trades off accuracy for faster performance. ✅
- [ ] It compares every vector in the dataset.
- [ ] It always guarantees 100% accuracy.
- [ ] It is slower than exact similarity search.

#### Q. What is the primary function of an embedding model in the context of vector search?
- [ ] To execute similarity search operations within a database
- [ ] To store vectors in a structured format for efficient retrieval
- [x] To transform text or data into numerical vector representations ✅
- [ ] To define the schema for a vector database

#### Q. What is the significance of using local ONNX models for embedding within the database?
- [x] Enhanced security because data remains within the database ✅
- [ ] Improved accuracy compared to external models
- [ ] Reduced embedding dimensions for faster processing
- [ ] Support for legacy SQL*Plus clients

#### Q. In Oracle Database 23ai, which SQL function is used to split text into words, sentences, or paragraphs for vector embedding preparation?
- [ ] VECTOR_EMBEDDING
- [x] VECTOR DISTANCE ✅
- [ ] VECTOR_NORM
- [ ] VECTOR_CHUNKS

#### Q. You are storing 1,000 embeddings in a VECTOR column, each with 256 dimensions using FLOAT32.
- [ ] What is the approximate size of the data on disk?
- [ ] 1GB
- [x] 1MB ✅
- [ ] 4MB
- [ ] 256 KB

#### Q. You need to generate a vector from the string '[1.2, 3.4]' in FLOAT32 format with 2 dimensions.
Which function will you use?
- [x] TO_VECTOR ✅
- [ ] VECTOR_SERIALIZE
- [ ] FROM_VECTOR
- [ ] VECTOR_DISTANCE

#### Q. Which function should you use to determine the storage format of a vector?
- [ ] VECTOR_NORM
- [ ] VECTOR _EMBEDDING
- [ ] VECTOR_CHUNKS
- [x] VECTOR_DIMENSION_FORMAT ✅

#### Q. What happens when querying with an IVF index if you increase the value of the NEIGHBOR PARTITION PROBES parameter?
- [ ] The number of centroids decreases.
- [ ] Accuracy decreases.
- [x] More partitions are probed, improving accuracy, but also increasing query latency. ✅
- [ ] Index creation time is reduced.

#### Q. machine learning team is using IVF indexes in Oracle Database 23ai to find similar images in a large dataset.
During testing, they observe that the search results are often incomplete, missing relevant images. They suspect the issue lies in the number of partitions probed.
How should they improve the search accuracy?
- [ ] Increase the VECTOR_MEMORY_S1ZE initialization parameter.
- [ ] Change the index type to HNSW for better accuracy.
- [ ] Re-create the index with a higher EFCONSTRUCTION value.
- [x] Add the TARGET ACCURACY clause to the query with a higher value for the accuracy. ✅

#### Q. Which SQL statement will successfully insert a vector into a table named my_table with a single VECTOR column named v?
- [x] INSERT INTO my_table VALUES ('{1.1, 2.2, 3.3}') ✅
- [ ] INSERT INTO my_table (v) VALUES (1.1, 2.2, 3.3)
- [ ] INSERT INTO my_table VALUES ((1.1, 2.2, 3.3))
- [ ] INSERT INTO my_table (v) VALUES ('[1.1, 2.2, 3.3]')

#### Q. What happens when you attempt to insert a vector with an incorrect number of dimensions into a VECTOR column with a defined number of dimensions?
- [x] The insert operation fails, and an error message is thrown. ✅
- [ ] The database ignores the defined dimensions and inserts the vector as is.
- [ ] The database truncates the vector to fit the defined dimensions.
- [ ] The database pads the vector with zeros to match the defined dimensions.

#### Q. What is the primary function of Select Al in Oracle Autonomous Database?
- [ ] To provide real-time data visualization and reporting tools integrated with Autonomous Database
- [ ] To eliminate the need for SQL expertise by enabling users to query data using natural language
- [ ] To eliminate the need for manual coding by automatically generating SQL queries for complex data analysis tasks
- [x] To improve the efficiency of Al applications by training machine learning models directly within the database ✅

#### Q. How is the security interaction between Autonomous Database and OCI Generative Al managed in the context of Select Al?
- [x] By utilizing Resource Principals, which grant the Autonomous Database instance access to OCI Generative AI without exposing sensitive credentials ✅
- [ ] By requiring users to manually enter their OCI API keys each time they execute a natural language query
- [ ] By establishing a secure VPN tunnel between the Autonomous Database and OCI Generative Al service
- [ ] By encrypting all communication between the Autonomous Database and OC! Generative Al using TLS/SSL protocols

#### Q. Which Oracle Cloud Infrastructure (OCI) service is directly integrated with Select AI?
- [x] OCI Generative Al ✅
- [ ] OCI Vision
- [ ] OCI Language
- [ ] OCI Data Science

#### Q. Which is NOT a feature or capability related to AI and Vector Search in Exadata?
- [ ] AI Smart Scan
- [x] Native Support for Vector Search Only within the Database Server ✅
- [ ] Vector Replication with GoldenGate
- [ ] Loading Vector Data using SQL*Loader

#### Q. Why would you choose to NOT define a specific size for the VECTOR column during development?
- [ ] It impacts the accuracy of similarity searches.
- [ ] It restricts the database to a single embedding model.
- [ ] It limits the length of text that can be vectorized.
- [x] Different external embedding models produce vectors with varying dimensions and data types. ✅

#### Q. In Oracle Database 23ai, which data type is used to store vector embeddings for similarity search?
- [ ] BLOB
- [ ] VARCHAR2
- [ ] VECTOR2
- [x] VECTOR ✅

#### Q. What is the primary purpose of a similarity search in Oracle Database 23ai?
- [ ] To find exact matches in BLOB data
- [x] To retrieve the most semantically similar entries using distance metrics between different vectors. ✅
- [ ] To optimize relational database operations
- [ ] To compute distances between all data points in a database

#### Q. What is the advantage of using Euclidean Squared Distance rather than Euclidean Distance in similarity search queries?
- [ ] It guarantees higher accuracy than Euclidean Distance.
- [ ] It is the default distance metric for Oracle Al Vector Search.
- [ ] It supports hierarchical partitioning of vectors.
- [x] It is simpler and faster because it avoids square-root calculations. ✅

#### Q. Which SQL query would retrieve the top-10 vectors based on Euclidean distance using exact similarity search?
- [x] SELECT docID FROM vector_tab
GROUP BY VECTOR_DISTANCE (embedding, :query_vector, EUCLIDEAN)
FETCH FIRST 10 ROWS ONLY; ✅
- [ ] SELECT docID FROM vector_tab
ORDER BY VECTOR_DISTANCE (embedding, :query_vector, COSINE)
FETCH EMACT FIRST 10 ROWS ONLY;
- [ ] SELECT docID FROM vector_tab
ORDER BY VECTOR_DISTANCE (embedding, :query_vector, EUCLIDEAN)
FETCH EXACT FIRST 10 ROWS ONLY;
- [ ] SELECT docID FROM vector_tab
WHERE VECTOR DISTANCE (embedding, :query_vector, EUCLIDEAN) < 10;

#### Q. What is the purpose of the VECTOR_DISTANCE function in Oracle Database 23ai similarity search?
- [ ] To create vector indexes for efficient searches
- [ ] To group vectors by their exact scores
- [x] To calculate the distance between vectors using a specified metric ✅
- [ ] To fetch rows that match exact vector embeddings

#### Q. Which SQL function is used to create a vector embedding for a given text string in Oracle Database 23ai?
- [ ] CREATE_VECTOR_EMBEDDING
- [ ] GENERATE_EMBEDDING
- [ ] EMBED_TEXT
- [x] VECTOR_EMBEDDING ✅

#### Q. Which PL/SQL function converts documents such as PDF, DOC, JSON, XML, or HTML to plain text?
- [x] DBMS_VECTOR_CHAIN.UTL_TO_TEXT ✅
- [ ] DBMS_VECTOR_CHAIN.UTIL_TO_CHUNKS
- [ ] DBMS_VECTOR.TEXT_TO_PLAIN
- [ ] DBMS_VECTOR.CONVERT_TO_TEXT

#### Q. Which PL/SQL package Is primarily used for interacting with Generative Al services in Oracle Database 23ai?
- [x] DBMS_VECTOR_CHAIN ✅
- [ ] DBMS_AI
- [ ] DBMS_GENAI
- [ ] DBMS_ML

#### Q. What is the primary purpose of the DBMS_VECTOR_CHAIN.UTL_TO_CHUNKS package in a RAG application?
- [ ] To load a document into the database
- [ ] To convert a document into a single, large text string
- [ ] To generate vector embeddings from a text document
- [x] To split a large document into smaller chunks to improve vector quality by minimizing token truncation ✅

#### Q. An application needs to fetch the top-3 matching sentences from a dataset of books while ensuring a balance between speed and accuracy.
- [ ] Which query structure should you use?
- [x] Multivector similarity search with approximate fetching and target accuracy ✅
- [ ] Approximate similarity search with the VECTOR_DISTANCE function
- [ ] Exact similarity search with Euclidean distance
- [ ] A combination of relational filters and similarity search

#### Q. You are tasked with finding the closest matching sentences across books, where each book has multiple paragraphs and sentences.
- [ ] Which SQL structure should you use?
- [ ] A nested query with ORDER BY
- [ ] Exact similarity search with a single query vector
- [ ] GROUP BY with vector operations
- [x] FETCH PARTITIONS BY clause ✅

#### Q. What is the default distance metric used by the VECTOR_DISTANCE function if none is specified?
- [ ] Manhattan
- [ ] Cosine
- [x] Euclidean ✅
- [ ] Hamming

#### Q. In Oracle Database 23ai, which SQL function calculates the distance between two vectors using the Euclidean metric?
- [ ] HAMMING_DISTANCE
- [ ] L1_DISTANCE
- [ ] COSINE_DISTANCE
- [x] L2_DISTANCE ✅
