# CodingInterview
C++exercise

void PrintContinousSeq(int begin, int end)
{
	for (int i = begin; i <= end; i++)
		cout << i << "   ";
	cout << endl;
}


//面试题57，和为S的连续正数序列
void FindContinousSeqOfSum(int sum)
{
	if (sum < 3)
		return;

	int begin = 1;
	int end = 2;
	int middle = (sum + 1) / 2;
	int curSum = begin + end;

	while (begin < middle)
	{
		if (curSum == sum)
			PrintContinousSeq(begin, end);

		while (curSum > sum&& begin < middle)
		{
			curSum -= begin;
			begin++;

			if (curSum == sum)
				PrintContinousSeq(begin, end);
		}
		end++;
		curSum += end;
	}
}
