# priorityQueue
priorityQueue by JS
用JS编写的优先级队列，支持自定义comparator<br>
调用方式如 <code>const pq=new PriorityQueue((a,b)=>a-b)</code>,默认的comparator是(a,b)=>(a-b),即入队的element越小，优先级越大。
