# Running Beastsnetwork Tests

To run all tests, run:

```bash
cd /path/to/beastsnetwork
make [-jn] debug-test # where n is number of compiler processes
```

To test a release build, replace `debug-test` with `release-test` in the previous command.

# Core tests

Core tests take longer than any other Beastsnetwork tests, due to the high amount of computational work involved in validating core components.

Tests are located in `tests/core_tests/`, and follow a straightforward naming convention. Most cases cover core functionality (`block_reward.cpp`, `chaingen.cpp`, `rct.cpp`, etc.), while some cover basic security tests (`double_spend.cpp` & `integer_overflow.cpp`).

To run only Beastsnetwork's core tests (after building):

```bash
cd build/debug/tests/core_tests
ctest
```

# Crypto Tests

Crypto tests are located under the `tests/crypto` directory.

- `crypto-tests.h` contains test harness headers
- `main.cpp` implements the driver for the crypto tests

Tests correspond to components under `src/crypto/`. 

To run only Beastsnetwork's crypto tests (after building):

```bash
cd build/debug/tests/crypto
ctest
```

# Functional tests

Functional tests are located under the `tests/functional_tests` directory.

Building all the tests requires installing the following dependencies:
```bash
pip install requests zmq deepdiff
```

First, run a regtest daemon in the offline mode and with a fixed difficulty:
```bash
beastsnetworkd --regtest --offline --fixed-difficulty 1
```

# Fuzz tests

Fuzz tests are written using American Fuzzy Lop (AFL), and located under the `tests/fuzz` directory.

# Hash tests

Hash tests exist under `tests/hash`, and include a set of target hashes in text files.

To run only Beastsnetwork's hash tests (after building):

```bash
cd build/debug/tests/hash
ctest
```

# Performance tests

Performance tests are located in `tests/performance_tests`, and test features for performance metrics on the host machine.

To run only Beastsnetwork's performance tests (after building):

```bash
cd build/debug/tests/performance_tests
./performance_tests
```

# Unit tests

Unit tests are defined under the `tests/unit_tests` directory. Independent components are tested individually to ensure they work properly on their own.

To run only Beastsnetwork's unit tests (after building):

```bash
cd build/debug/tests/unit_tests
ctest
```

# Writing new tests

## Test hygiene

When writing new tests, please implement all functions in `.cpp` or `.c` files, and only put function headers in `.h` files.
