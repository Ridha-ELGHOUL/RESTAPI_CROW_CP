FROM bbox:latest

WORKDIR /usr/src/cppweb/demo_crow
COPY . .

WORKDIR /usr/src/cppweb/demo_crow/build
RUN cmake .
RUN make
CMD ["./demo_crow"]
