test-teradata:
	dbt deps
	dbt seed --target teradata --full-refresh
	dbt run -s test_insert_by_period --target teradata --full-refresh
	dbt test
	dbt run -s test_insert_by_period --target teradata --vars 'test_backfill: True'
	dbt test --target teradata

test-all: test-teradata
	echo "Completed successfully"
