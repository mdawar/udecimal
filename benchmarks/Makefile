
bench:
	# @go test -bench BenchmarkMarshalJSON -benchmem -memprofile mem.out -cpuprofile cpu.out -run NONE
	@go test -bench BenchmarkMarshalJSON -benchmem -count=10 -run NONE > new.txt

bench-udec:
	@rm -f bench-udec.txt
	@go test -bench=./udec -benchmem -count=10 -timeout=1h> bench-udec.txt
	@sed -i 's/udec\///g' bench-udec.txt

bench-ss:
	@rm -f bench-ss.txt
	@go test -bench=./ss -benchmem -count=10 -timeout=1h> bench-ss.txt
	@sed -i 's/ss\///g' bench-ss.txt
	
bench-ed:
	@rm -f bench-ed.txt
	@go test -bench=./eric -benchmem -count=10 -timeout=1h> bench-ed.txt
	@sed -i 's/eric\///g' bench-ed.txt

stats:
	@benchstat shopspring=bench-ss.txt udecimal=bench-udec.txt > bench-vs-shopspring.txt
	@benchstat ericlagergren=bench-ed.txt udecimal=bench-udec.txt > bench-vs-ericlagergren.txt
