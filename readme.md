
# Distributed System Process Scheduling Algorithm

This project implements a process scheduling algorithm for a distributed system that handles millions of transactions per day on an e-commerce platform. The system consists of multiple servers, each running different services that manage specific types of transactions, such as payment processing or order processing.

## Features

- **Service Management**: Each service has a pool of worker threads responsible for processing incoming requests.
- **Priority-Based Scheduling**: Worker threads are assigned priority levels that determine the order of request processing.
- **Resource Management**: Each worker thread has a specified amount of resources, which limits the number of requests it can handle simultaneously.
- **Efficient Resource Allocation**: The scheduling algorithm prioritizes high-priority worker threads, ensuring that resources are allocated efficiently.
- **Request Handling**: The algorithm processes requests based on transaction type, and dynamically assigns them to appropriate worker threads.

## Input/Output

### Input
- **Number of Services**: Total number of services running in the system.
- **Number of Worker Threads**: Total number of worker threads available for each service.
- **Worker Thread Configuration**: For each service, input the priority level and resources assigned to each worker thread.
- **Transactions**: List of transactions, including the type of transaction and the resources required.

### Output
- **Order of Request Processing**: The order in which the requests were processed by the worker threads.
- **Average Waiting Time**: Average time a request waits before being processed.
- **Average Turnaround Time**: Average time taken to complete the processing of a request.
- **Rejected Requests**: Number of requests rejected due to insufficient resources.
- **High Traffic Information**: During periods of high traffic, the number of requests forced to wait due to lack of available resources and the number of blocked requests.

## Implementation Details

### Worker Threads
- **Function**: The `worker()` function simulates a worker thread that processes transactions. Each worker thread checks for assigned transactions and processes them based on its priority and available resources.

### Service Manager
- **Function**: The `service_manager()` function manages the allocation of transactions to worker threads. It continuously monitors the incoming transaction queue and assigns transactions to available worker threads based on their priority and resource availability.

### Statistics
- **Function**: The `print_stats()` function calculates and displays statistics, including average waiting time, average turnaround time, and additional details during high traffic periods.

## Example Usage

1. **Compile and Run the Program**:
   ```bash
   g++ -std=c++11 -o scheduler scheduler.cpp -lpthread
   ./scheduler
   ```

2. **Provide the Input**:
   - Enter the number of services.
   - Enter the number of worker threads for each service.
   - Provide the priority level and resources for each worker thread.
   - Enter the number of transactions and their details.

3. **View the Output**:
   - The program will display the order in which requests were processed.
   - It will also show average waiting time, average turnaround time, and other relevant statistics.

