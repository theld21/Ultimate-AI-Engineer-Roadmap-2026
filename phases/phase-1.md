## 🗺️ PHASE 1 - Programming Foundation

> **Goal:** Write clean, production-quality Python. This is non-negotiable.

### 1.1 Python Fundamentals

**Data Types & Variables**
- Integers, floats, strings, booleans, None
- Type conversion: `int()`, `float()`, `str()`, `bool()`
- `type()` and `isinstance()`
- Mutable vs immutable types - critical for AI pipelines

**Strings**
- String slicing: `s[start:stop:step]`
- Methods: `split`, `join`, `strip`, `replace`, `find`, `startswith`, `endswith`
- f-strings: `f"value is {x:.2f}"`
- Multiline strings with triple quotes

**Collections**
- Lists - indexing, slicing, `append`, `extend`, `pop`, `sort`, `reverse`
- Tuples - immutability and when to prefer over lists
- Dictionaries - CRUD, `.keys()`, `.values()`, `.items()`, `.get()`
- Sets - uniqueness, union, intersection, difference
- Nested collections - list of dicts, dict of lists

**Control Flow**
- `if / elif / else`
- `for` loops - iterating over lists, dicts, ranges
- `while` loops and `break / continue`
- `range()`, `enumerate()`, `zip()`

### 1.2 Functions

- Defining functions with `def`
- Positional vs keyword arguments
- Default argument values
- `*args` and `**kwargs` - used constantly in AI SDKs
- Return values, tuple unpacking
- Lambda functions
- Recursion
- Docstrings

### 1.3 Object-Oriented Programming

- Classes and instances
- `__init__` constructor
- Instance methods and `self`
- Class vs instance variables
- Inheritance and `super()`
- Overriding methods
- `__repr__`, `__str__`, `__len__`, `__getitem__`
- `@property`, `@staticmethod`, `@classmethod`
- Abstract classes with `ABC` - used heavily in LangChain, LlamaIndex

### 1.4 Pythonic Code & Idioms

- List, dict, set comprehensions
- Generator expressions - memory efficient for large datasets
- `map()`, `filter()`, `reduce()`
- Unpacking: `a, b, *rest = lst`
- `any()`, `all()`, `sorted()` with `key=`
- `collections` module: `Counter`, `defaultdict`, `deque`

### 1.5 File I/O & Data Handling

- Reading/writing text files with `open()` and context managers
- Reading CSVs with `csv` module
- Reading/writing JSON: `json.load()`, `json.dump()`
- Pickle: `pickle.dump()`, `pickle.load()`
- `os` module: path joining, listing dirs, making dirs
- `pathlib.Path` - modern file path handling
- `glob` - pattern matching files (useful for batch processing)

### 1.6 Error Handling & Debugging

- `try / except / finally`
- Catching specific exceptions
- Raising exceptions: `raise ValueError("message")`
- Custom exception classes
- `logging` module - DEBUG, INFO, WARNING, ERROR
- `pdb` and `breakpoint()`
- Reading tracebacks

### 1.7 Performance & Memory

- Generators and `yield` - critical for streaming AI responses
- `itertools` module
- `timeit` and `cProfile` for benchmarking
- Shallow vs deep copy
- Vectorization preference over Python loops

### 1.8 NumPy (Non-Negotiable for AI)

- Array creation: `np.array()`, `np.zeros()`, `np.ones()`, `np.eye()`
- Array shape, ndim, dtype
- Reshaping: `reshape()`, `flatten()`, `ravel()`
- Stacking: `np.stack()`, `np.hstack()`, `np.vstack()`
- Boolean indexing, `np.where()`
- Broadcasting rules
- `np.dot()` and `@` operator
- Matrix operations: `np.linalg.inv()`, `np.linalg.eig()`
- Aggregations with `axis=` argument
- `np.random` module

### 1.9 Pandas (Essential for Data Work)

- DataFrames & Series creation
- `df.head()`, `df.info()`, `df.describe()`, `df.shape`
- `loc` vs `iloc` indexing
- Boolean filtering
- Handling missing values: `isna()`, `dropna()`, `fillna()`
- `groupby()`, `agg()`, `pivot_table()`, `value_counts()`
- `merge()`, `concat()`, `melt()`, `pivot()`
- Parsing dates: `pd.to_datetime()`

### 1.10 Code Quality & Project Structure

- Virtual environments: `venv` or `conda`
- `requirements.txt` and `pip freeze`
- Writing modular code - splitting into files and modules
- `__init__.py` - making a folder a package
- Type hints: `def fn(x: int) -> str:`
- `dataclasses` - cleaner data containers
- Unit tests with `pytest`
- Linting with `ruff` or `flake8`, formatting with `black`

### 1.11 Python for AI Workflows

- Jupyter notebooks - cells, magic commands
- Google Colab - GPU access
- `tqdm` - progress bars for training loops
- `argparse` - CLI arguments for scripts
- `hydra` or `yaml` configs - managing experiment configs
- `dotenv` - managing API keys (CRITICAL for AI projects)
- Seeding for reproducibility: `random`, `numpy`, `torch`
- Saving/loading models: `pickle`, `joblib`, `torch.save()`

### 1.12 Async Python (Critical for AI APIs)

- `async/await` syntax
- `asyncio` event loop
- `aiohttp` - async HTTP calls to AI APIs
- Concurrent API calls with `asyncio.gather()`
- `httpx` - async-first HTTP client used in production AI apps
- Understanding why streaming LLM responses need async

---

### 📦 Phase 1 Projects

**🟢 Easy: Python AI Toolkit CLI**
- Build a CLI tool that accepts text input and calls the OpenAI API
- Features: summarize, translate, sentiment analysis
- Stack: Python, `argparse`, `openai` SDK, `.env`

**🟡 Medium: Async Multi-API Caller**
- Call OpenAI + Anthropic + Gemini simultaneously with `asyncio.gather()`
- Compare responses side by side
- Add error handling, retries with exponential backoff
- Stack: Python, `httpx`, `asyncio`, `rich` for terminal display

**🔴 Hard: Production-Grade Data Pipeline**
- Build a pipeline that reads CSVs, cleans data, chunks into batches, and sends to an embedding API
- Features: progress bars, error recovery, resume from checkpoint, async batching
- Stack: Python, Pandas, NumPy, `tqdm`, `asyncio`, OpenAI Embeddings API

---

