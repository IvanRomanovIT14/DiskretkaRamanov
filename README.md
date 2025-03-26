#include <iostream>
#include <map>
#include <vector>
#include <algorithm>
#include <Windows.h>
#include <string>
using namespace std;
bool gg(pair<char, int>& m, pair<char, int>& g) {
	return m.second > g.second;
}
int main() {
	SetConsoleCP(1251);
	SetConsoleOutputCP(1251);
	string str = "ОНА ЗАБОТЛИВО ПОГЛЯДЫВАЛА НА НЕГО В ТО ВРЕМЯ КАК ОН ПОДОШЕЛ ПОСЛУШАТЬ ТО ЧТО ГОВОРИЛОСЬ ОКОЛО МОРТЕМАРА И ОТОШЕЛ К ДРУГОМУ КРУЖКУ ГДЕ ГОВОРИЛ АББАТ ДЛЯ ПЬЕРА ВОСПИТАННОГО ЗА ГРАНИЦЕЙ ЭТОТ ВЕЧЕР АННЫ ПАВЛОВНЫ БЫЛ ПЕРВЫЙ КОТОРЫЙ ОН ВИДЕЛ В РОССИИ ОН ЗНАЛ ЧТО ТУТ СОБРАНА ВСЯ ИНТЕЛЛИГЕНЦИЯ ПЕТЕРБУРГА И У НЕГО КАК У РЕБЕНКА В ИГРУШЕЧНОЙ ЛАВКЕ РАЗБЕГАЛИСЬ ГЛАЗА ОН ВСЕ БОЯЛСЯ ПРОПУСТИТЬ УМНЫЕ РАЗГОВОРЫ КОТОРЫЕ ОН МОЖЕТ УСЛЫХАТЬ ГЛЯДЯ НА УВЕРЕННЫЕ И ИЗЯЩНЫЕ ВЫРАЖЕНИЯ ЛИЦ СОБРАННЫХ ЗДЕСЬ ОН ВСЕ ЖДАЛ ЧЕГО НИБУДЬ ОСОБЕННО УМНОГО НАКОНЕЦ ОН ПОДОШЕЛ К МОРИО РАЗГОВОР ПОКАЗАЛСЯ ЕМУ ИНТЕРЕСЕН И ОН ОСТАНОВИЛСЯ ОЖИДАЯ СЛУЧАЯ ВЫСКАЗАТЬ СВОИ МЫСЛИ КАК ЭТО ЛЮБЯТ МОЛОДЫЕ ЛЮДИ";
	map<char, int> cnt;
	for (char n : str) {
		cnt[n]++;
	}
	vector<pair<char, int>> symvec(cnt.begin(),cnt.end());
	sort(symvec.begin(), symvec.end(), gg);
	cout << "Количество каждого символа в тексте по убыванию: " << endl;
	for (auto& pair : symvec) {
		cout << pair.first << ": " << pair.second << endl;
	}
	int res = str.size();
	cout << "Общее количество символов: " << res << endl;
}
