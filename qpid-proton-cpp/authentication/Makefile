CCFLAGS := -Os -std=c++11 -lstdc++
TARGETS := kerberos

.PHONY: build
build: ${TARGETS}

.PHONY: clean
clean:
	rm -f ${TARGETS}

.PHONY: test
test: build
	KRB5_TRACE=/dev/stdout ./kerberos upto.nogood.industries

%: %.cpp
	${CXX} $< -o $@ ${CCFLAGS} -lqpid-proton -lqpid-proton-cpp
