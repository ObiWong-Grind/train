# Study

How many days to learn Python3?

    import time


    class TimeMachine:
        """
            时间机器
        """
        def __init__(self, year, mouth, day):
            """
            :param year: 年 int
            :param mouth: 月 int
            :param day: 日 int
            """
            self.year = year
            self.mouth = mouth
            self.day = day

        def __get_seconds(self):
            """
                计算总秒数
            :return: 总秒数 int
            """
            self.tuple_time = time.strptime("%d年%d月%d日" % (self.year, self.mouth, self.day), "%Y年%m月%d日")
            return int(time.time() - time.mktime(self.tuple_time))

        def learn_days(self):
            """
                计算总天数
            :return: 总天数 int
            """
            seconds = self.__get_seconds()
            return seconds // (24 * 60 ** 2)


    time01 = TimeMachine(2019, 7, 1)
    print("%d days of learning Python3" % time01.learn_days())


